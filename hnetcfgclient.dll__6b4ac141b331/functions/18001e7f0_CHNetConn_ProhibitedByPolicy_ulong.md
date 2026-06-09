# CHNetConn::ProhibitedByPolicy(ulong)

- ea: `0x18001e7f0`
- end: `0x18001e915`
- name: `?ProhibitedByPolicy@CHNetConn@@IEAAEK@Z`
- size: `293`
- prototype: `unsigned __int8 __fastcall(CHNetConn *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800203b0`
- `0x180020930`
- `0x180025e80`
- `0x180026300`
- `0x1800275a0`
- `0x180027860`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180018090`
- `0x18001e7f0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e8b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e8b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e84d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e84d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e873`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e873`

## pseudocode

```c
bool __fastcall CHNetConn::ProhibitedByPolicy(CHNetConn *this, unsigned int a2)
{
  _QWORD *v4; // rbx
  int v5; // esi
  bool v6; // di
  HRESULT Instance; // eax
  __int64 v8; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 311, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v4 = (_QWORD *)((char *)this + 128);
  if ( *((_QWORD *)this + 16) )
    goto LABEL_13;
  v5 = 0;
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*v4 )
  {
    Instance = CoCreateInstance(
                 &CLSID_NetConnectionUiUtilities,
                 0,
                 0x8005u,
                 &GUID_faedcf5e_31fe_11d1_aad2_00805fc1270e,
                 (LPVOID *)this + 16);
    v5 = Instance;
    if ( Instance < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        312,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)Instance);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v5 >= 0 )
LABEL_13:
    v6 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 48LL))(*v4, a2) == 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v8) = v6;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v8);
  }
  return v6;
}

```

## disassembly

```asm
0x18001e7f0  push    rbx
0x18001e7f2  push    rbp
0x18001e7f3  push    rsi
0x18001e7f4  push    rdi
0x18001e7f5  push    r12
0x18001e7f7  push    r14
0x18001e7f9  sub     rsp, 38h
0x18001e7fd  mov     r14d, edx
0x18001e800  mov     rbp, rcx
0x18001e803  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e80a  lea     r12, WPP_GLOBAL_Control
0x18001e811  cmp     rcx, r12
0x18001e814  jz      short loc_18001E837
0x18001e816  test    byte ptr [rcx+1Ch], 8
0x18001e81a  jz      short loc_18001E837
0x18001e81c  cmp     byte ptr [rcx+19h], 6
0x18001e820  jb      short loc_18001E837
0x18001e822  mov     rcx, [rcx+10h]
0x18001e826  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e82d  mov     edx, 137h
0x18001e832  call    WPP_SF_
0x18001e837  lea     rbx, [rbp+80h]
0x18001e83e  cmp     qword ptr [rbx], 0
0x18001e842  jnz     short loc_18001E8BD
0x18001e844  lea     rcx, [rbp+10h]; lpCriticalSection
0x18001e848  xor     esi, esi
0x18001e84a  xor     dil, dil
0x18001e84d  call    cs:__imp_EnterCriticalSection
0x18001e853  cmp     [rbx], rsi
0x18001e856  jnz     short loc_18001E8AF
0x18001e858  lea     r9, _GUID_faedcf5e_31fe_11d1_aad2_00805fc1270e; riid
0x18001e85f  mov     [rsp+68h+ppv], rbx; ppv
0x18001e864  xor     edx, edx; pUnkOuter
0x18001e866  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x18001e86d  mov     r8d, 8005h; dwClsContext
0x18001e873  call    cs:__imp_CoCreateInstance
0x18001e879  mov     esi, eax
0x18001e87b  test    eax, eax
0x18001e87d  jns     short loc_18001E8AF
0x18001e87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e886  cmp     rcx, r12
0x18001e889  jz      short loc_18001E8AF
0x18001e88b  test    byte ptr [rcx+1Ch], 8
0x18001e88f  jz      short loc_18001E8AF
0x18001e891  cmp     byte ptr [rcx+19h], 2
0x18001e895  jb      short loc_18001E8AF
0x18001e897  mov     rcx, [rcx+10h]
0x18001e89b  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e8a2  mov     edx, 138h
0x18001e8a7  mov     r9d, eax
0x18001e8aa  call    WPP_SF_d
0x18001e8af  lea     rcx, [rbp+10h]; lpCriticalSection
0x18001e8b3  call    cs:__imp_LeaveCriticalSection
0x18001e8b9  test    esi, esi
0x18001e8bb  js      short loc_18001E8D5
0x18001e8bd  mov     rcx, [rbx]
0x18001e8c0  mov     edx, r14d
0x18001e8c3  mov     rax, [rcx]
0x18001e8c6  mov     rax, [rax+30h]
0x18001e8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8cf  test    eax, eax
0x18001e8d1  setz    dil
0x18001e8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8dc  cmp     rcx, r12
0x18001e8df  jz      short loc_18001E905
0x18001e8e1  test    byte ptr [rcx+1Ch], 8
0x18001e8e5  jz      short loc_18001E905
0x18001e8e7  cmp     byte ptr [rcx+19h], 6
0x18001e8eb  jb      short loc_18001E905
0x18001e8ed  mov     rcx, [rcx+10h]
0x18001e8f1  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e8f8  mov     edx, 139h
0x18001e8fd  mov     r9b, dil
0x18001e900  call    WPP_SF_c
0x18001e905  mov     al, dil
0x18001e908  add     rsp, 38h
0x18001e90c  pop     r14
0x18001e90e  pop     r12
0x18001e910  pop     rdi
0x18001e911  pop     rsi
0x18001e912  pop     rbp
0x18001e913  pop     rbx
0x18001e914  retn
```
