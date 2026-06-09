# CHNetConn::UpdateNetman(void)

- ea: `0x180021458`
- end: `0x18002159d`
- name: `?UpdateNetman@CHNetConn@@IEAAJXZ`
- size: `325`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001a820`
- `0x1800203b0`
- `0x180020930`
- `0x180025610`
- `0x180026300`
- `0x1800268c0`
- `0x1800274d0`
- `0x1800275a0`
- `0x180027860`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180021458`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021512`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800214ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800214ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800214d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800214d2`

## pseudocode

```c
__int64 __fastcall CHNetConn::UpdateNetman(CHNetConn *this)
{
  _QWORD *v2; // rdi
  unsigned int v3; // ebx
  HRESULT Instance; // eax
  int v5; // eax
  PVOID *v6; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v2 = (_QWORD *)((char *)this + 136);
  if ( !*((_QWORD *)this + 17) )
  {
    v3 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( !*v2 )
    {
      Instance = CoCreateInstance(
                   &CLSID_NetConnectionHNetUtil,
                   0,
                   0x8005u,
                   &GUID_faedcf64_31fe_11d1_aad2_00805fc1270e,
                   (LPVOID *)this + 17);
      v3 = Instance;
      if ( Instance < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          315,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)Instance);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( (v3 & 0x80000000) != 0 )
      goto LABEL_18;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 24LL))(*v2);
  v3 = v5;
  if ( v5 >= 0 )
    goto LABEL_18;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      316,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)v5);
LABEL_18:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 317, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180021458  push    rbx
0x18002145a  push    rsi
0x18002145b  push    rdi
0x18002145c  push    r14
0x18002145e  sub     rsp, 38h
0x180021462  mov     rsi, rcx
0x180021465  mov     rcx, cs:WPP_GLOBAL_Control
0x18002146c  lea     r14, WPP_GLOBAL_Control
0x180021473  cmp     rcx, r14
0x180021476  jz      short loc_180021499
0x180021478  test    byte ptr [rcx+1Ch], 8
0x18002147c  jz      short loc_180021499
0x18002147e  cmp     byte ptr [rcx+19h], 6
0x180021482  jb      short loc_180021499
0x180021484  mov     rcx, [rcx+10h]
0x180021488  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002148f  mov     edx, 13Ah
0x180021494  call    WPP_SF_
0x180021499  lea     rdi, [rsi+88h]
0x1800214a0  cmp     qword ptr [rdi], 0
0x1800214a4  jnz     short loc_18002151C
0x1800214a6  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800214aa  xor     ebx, ebx
0x1800214ac  call    cs:__imp_EnterCriticalSection
0x1800214b2  cmp     [rdi], rbx
0x1800214b5  jnz     short loc_18002150E
0x1800214b7  lea     r9, _GUID_faedcf64_31fe_11d1_aad2_00805fc1270e; riid
0x1800214be  mov     [rsp+58h+ppv], rdi; ppv
0x1800214c3  xor     edx, edx; pUnkOuter
0x1800214c5  lea     rcx, CLSID_NetConnectionHNetUtil; rclsid
0x1800214cc  mov     r8d, 8005h; dwClsContext
0x1800214d2  call    cs:__imp_CoCreateInstance
0x1800214d8  mov     ebx, eax
0x1800214da  test    eax, eax
0x1800214dc  jns     short loc_18002150E
0x1800214de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214e5  cmp     rcx, r14
0x1800214e8  jz      short loc_18002150E
0x1800214ea  test    byte ptr [rcx+1Ch], 8
0x1800214ee  jz      short loc_18002150E
0x1800214f0  cmp     byte ptr [rcx+19h], 2
0x1800214f4  jb      short loc_18002150E
0x1800214f6  mov     rcx, [rcx+10h]
0x1800214fa  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180021501  mov     edx, 13Bh
0x180021506  mov     r9d, eax
0x180021509  call    WPP_SF_d
0x18002150e  lea     rcx, [rsi+10h]; lpCriticalSection
0x180021512  call    cs:__imp_LeaveCriticalSection
0x180021518  test    ebx, ebx
0x18002151a  js      short loc_180021561
0x18002151c  mov     rcx, [rdi]
0x18002151f  mov     rax, [rcx]
0x180021522  mov     rax, [rax+18h]
0x180021526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002152b  mov     ebx, eax
0x18002152d  test    eax, eax
0x18002152f  jns     short loc_180021561
0x180021531  mov     rcx, cs:WPP_GLOBAL_Control
0x180021538  cmp     rcx, r14
0x18002153b  jz      short loc_180021591
0x18002153d  test    byte ptr [rcx+1Ch], 8
0x180021541  jz      short loc_180021568
0x180021543  cmp     byte ptr [rcx+19h], 2
0x180021547  jb      short loc_180021568
0x180021549  mov     rcx, [rcx+10h]
0x18002154d  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180021554  mov     edx, 13Ch
0x180021559  mov     r9d, eax
0x18002155c  call    WPP_SF_d
0x180021561  mov     rcx, cs:WPP_GLOBAL_Control
0x180021568  cmp     rcx, r14
0x18002156b  jz      short loc_180021591
0x18002156d  test    byte ptr [rcx+1Ch], 8
0x180021571  jz      short loc_180021591
0x180021573  cmp     byte ptr [rcx+19h], 6
0x180021577  jb      short loc_180021591
0x180021579  mov     rcx, [rcx+10h]
0x18002157d  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180021584  mov     edx, 13Dh
0x180021589  mov     r9d, ebx
0x18002158c  call    WPP_SF_d
0x180021591  mov     eax, ebx
0x180021593  add     rsp, 38h
0x180021597  pop     r14
0x180021599  pop     rdi
0x18002159a  pop     rsi
0x18002159b  pop     rbx
0x18002159c  retn
```
