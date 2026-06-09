# HrCreateNetConnectionUtilities(INetConnectionUiUtilities * *)

- ea: `0x18001d7b8`
- end: `0x18001d8a6`
- name: `?HrCreateNetConnectionUtilities@@YAJPEAPEAUINetConnectionUiUtilities@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e130`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001d7b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d828`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d828`

## pseudocode

```c
__int64 __fastcall HrCreateNetConnectionUtilities(LPVOID *ppv)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  HRESULT Instance; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = -2147024809;
  if ( !ppv )
    goto LABEL_12;
  Instance = CoCreateInstance(&CLSID_NetConnectionUiUtilities, 0, 1u, &IID_INetConnectionUiUtilities, ppv);
  v3 = Instance;
  if ( Instance >= 0 )
    goto LABEL_11;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)Instance);
LABEL_11:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 12, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001d7b8  mov     [rsp+arg_0], rbx
0x18001d7bd  mov     [rsp+arg_8], rbp
0x18001d7c2  push    rdi
0x18001d7c3  sub     rsp, 30h
0x18001d7c7  mov     rdi, rcx
0x18001d7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7d1  lea     rbp, WPP_GLOBAL_Control
0x18001d7d8  cmp     rcx, rbp
0x18001d7db  jz      short loc_18001D805
0x18001d7dd  test    byte ptr [rcx+1Ch], 8
0x18001d7e1  jz      short loc_18001D805
0x18001d7e3  cmp     byte ptr [rcx+19h], 6
0x18001d7e7  jb      short loc_18001D805
0x18001d7e9  mov     rcx, [rcx+10h]
0x18001d7ed  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d7f4  mov     edx, 0Ah
0x18001d7f9  call    WPP_SF_
0x18001d7fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d805  mov     ebx, 80070057h
0x18001d80a  test    rdi, rdi
0x18001d80d  jz      short loc_18001D86B
0x18001d80f  xor     edx, edx; pUnkOuter
0x18001d811  mov     [rsp+38h+ppv], rdi; ppv
0x18001d816  lea     r9, IID_INetConnectionUiUtilities; riid
0x18001d81d  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x18001d824  lea     r8d, [rdx+1]; dwClsContext
0x18001d828  call    cs:__imp_CoCreateInstance
0x18001d82e  mov     ebx, eax
0x18001d830  test    eax, eax
0x18001d832  jns     short loc_18001D864
0x18001d834  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d83b  cmp     rcx, rbp
0x18001d83e  jz      short loc_18001D894
0x18001d840  test    byte ptr [rcx+1Ch], 8
0x18001d844  jz      short loc_18001D86B
0x18001d846  cmp     byte ptr [rcx+19h], 2
0x18001d84a  jb      short loc_18001D86B
0x18001d84c  mov     rcx, [rcx+10h]
0x18001d850  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d857  mov     edx, 0Bh
0x18001d85c  mov     r9d, eax
0x18001d85f  call    WPP_SF_d
0x18001d864  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d86b  cmp     rcx, rbp
0x18001d86e  jz      short loc_18001D894
0x18001d870  test    byte ptr [rcx+1Ch], 8
0x18001d874  jz      short loc_18001D894
0x18001d876  cmp     byte ptr [rcx+19h], 6
0x18001d87a  jb      short loc_18001D894
0x18001d87c  mov     rcx, [rcx+10h]
0x18001d880  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d887  mov     edx, 0Ch
0x18001d88c  mov     r9d, ebx
0x18001d88f  call    WPP_SF_d
0x18001d894  mov     rbp, [rsp+38h+arg_8]
0x18001d899  mov     eax, ebx
0x18001d89b  mov     rbx, [rsp+38h+arg_0]
0x18001d8a0  add     rsp, 30h
0x18001d8a4  pop     rdi
0x18001d8a5  retn
```
