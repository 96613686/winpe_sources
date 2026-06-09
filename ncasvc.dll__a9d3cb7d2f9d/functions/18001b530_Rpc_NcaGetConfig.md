# Rpc_NcaGetConfig

- ea: `0x18001b530`
- end: `0x18001b67a`
- name: `Rpc_NcaGetConfig`
- size: `330`
- prototype: `__int64 __fastcall(void *, struct NCA_INTSERVER_ENGINE_HANDLE_ *, unsigned int, _DWORD *, int, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180004f34`
- `0x180007b58`
- `0x180019784`
- `0x18001b160`
- `0x18001b530`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b56a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b65b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b56a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b65b`

## pseudocode

```c
__int64 __fastcall Rpc_NcaGetConfig(
        void *a1,
        struct NCA_INTSERVER_ENGINE_HANDLE_ *a2,
        unsigned int a3,
        _DWORD *a4,
        int a5,
        _DWORD *a6,
        _DWORD *a7)
{
  _DWORD *v11; // rdi
  _DWORD *v12; // rsi
  __int64 v13; // rcx
  int Config; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  bool v17; // sf
  LARGE_INTEGER v19; // [rsp+30h] [rbp-48h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-40h] BYREF

  v19.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&v19);
  v11 = a6;
  v12 = a7;
  *a6 = 0;
  *v12 = 0;
  Config = NcaRpcAPIsSecModeAccessCheckForClient(0, 1, a1);
  if ( Config < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 22;
LABEL_16:
      WPP_SF_d(v15[2], v16, &WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids, (unsigned int)Config);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  Config = SvrImpl_NcaGetConfig(v13, a2, a3, a4, (unsigned int *)&a5);
  if ( !Config )
  {
    *v11 = a5;
LABEL_11:
    v17 = Config < 0;
    goto LABEL_12;
  }
  *v11 = 0;
  if ( Config == 234 )
  {
    *v12 = a5;
LABEL_10:
    Config = (unsigned __int16)Config | 0x80070000;
    goto LABEL_11;
  }
  v17 = Config < 0;
  if ( Config > 0 )
    goto LABEL_10;
LABEL_12:
  if ( v17 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 23;
      goto LABEL_16;
    }
  }
LABEL_17:
  QueryPerformanceCounter(&PerformanceCount);
  return NcaHResultToWindowsError(Config);
}

```

## disassembly

```asm
0x18001b530  mov     r11, rsp
0x18001b533  push    rbx
0x18001b534  push    rbp
0x18001b535  push    rsi
0x18001b536  push    rdi
0x18001b537  push    r14
0x18001b539  push    r15
0x18001b53b  sub     rsp, 48h
0x18001b53f  mov     eax, [rsp+78h+arg_20]
0x18001b546  mov     rbx, rcx
0x18001b549  lea     rcx, [r11-48h]; lpPerformanceCount
0x18001b54d  mov     [r11+28h], eax
0x18001b551  mov     rbp, r9
0x18001b554  mov     qword ptr [r11-48h], 0
0x18001b55c  mov     r14d, r8d
0x18001b55f  mov     qword ptr [r11-40h], 0
0x18001b567  mov     r15, rdx
0x18001b56a  call    cs:__imp_QueryPerformanceCounter
0x18001b571  nop     dword ptr [rax+rax+00h]
0x18001b576  mov     rdi, [rsp+78h+arg_28]
0x18001b57e  mov     r8, rbx
0x18001b581  mov     rsi, [rsp+78h+arg_30]
0x18001b589  mov     edx, 1
0x18001b58e  xor     ecx, ecx
0x18001b590  mov     dword ptr [rdi], 0
0x18001b596  mov     dword ptr [rsi], 0
0x18001b59c  call    NcaRpcAPIsSecModeAccessCheckForClient
0x18001b5a1  mov     ebx, eax
0x18001b5a3  test    eax, eax
0x18001b5a5  jns     short loc_18001B5CF
0x18001b5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5ae  lea     rax, WPP_GLOBAL_Control
0x18001b5b5  cmp     rcx, rax
0x18001b5b8  jz      loc_18001B656
0x18001b5be  test    byte ptr [rcx+1Ch], 1
0x18001b5c2  jz      loc_18001B656
0x18001b5c8  mov     edx, 16h
0x18001b5cd  jmp     short loc_18001B643
0x18001b5cf  lea     rax, [rsp+78h+arg_20]
0x18001b5d7  mov     r9, rbp
0x18001b5da  mov     r8d, r14d
0x18001b5dd  mov     [rsp+78h+var_58], rax
0x18001b5e2  mov     rdx, r15
0x18001b5e5  call    ?SvrImpl_NcaGetConfig@@YAKPEAX0W4NCA_CONFIG_@@PEAEPEAK@Z; SvrImpl_NcaGetConfig(void *,void *,NCA_CONFIG_,uchar *,ulong *)
0x18001b5ea  mov     ebx, eax
0x18001b5ec  test    eax, eax
0x18001b5ee  jnz     short loc_18001B5FB
0x18001b5f0  mov     eax, [rsp+78h+arg_20]
0x18001b5f7  mov     [rdi], eax
0x18001b5f9  jmp     short loc_18001B621
0x18001b5fb  mov     dword ptr [rdi], 0
0x18001b601  cmp     ebx, 0EAh
0x18001b607  jnz     short loc_18001B614
0x18001b609  mov     eax, [rsp+78h+arg_20]
0x18001b610  mov     [rsi], eax
0x18001b612  jmp     short loc_18001B618
0x18001b614  test    ebx, ebx
0x18001b616  jle     short loc_18001B623
0x18001b618  movzx   ebx, bx
0x18001b61b  or      ebx, 80070000h
0x18001b621  test    ebx, ebx
0x18001b623  jns     short loc_18001B656
0x18001b625  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b62c  lea     rax, WPP_GLOBAL_Control
0x18001b633  cmp     rcx, rax
0x18001b636  jz      short loc_18001B656
0x18001b638  test    byte ptr [rcx+1Ch], 1
0x18001b63c  jz      short loc_18001B656
0x18001b63e  mov     edx, 17h
0x18001b643  mov     rcx, [rcx+10h]
0x18001b647  lea     r8, WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids
0x18001b64e  mov     r9d, ebx
0x18001b651  call    WPP_SF_d
0x18001b656  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x18001b65b  call    cs:__imp_QueryPerformanceCounter
0x18001b662  nop     dword ptr [rax+rax+00h]
0x18001b667  mov     ecx, ebx
0x18001b669  add     rsp, 48h
0x18001b66d  pop     r15
0x18001b66f  pop     r14
0x18001b671  pop     rdi
0x18001b672  pop     rsi
0x18001b673  pop     rbp
0x18001b674  pop     rbx
0x18001b675  jmp     NcaHResultToWindowsError
```
