# CSecConLib::InternalInitIfNecessary(void)

- ea: `0x18000f1c0`
- end: `0x18000f292`
- name: `?InternalInitIfNecessary@CSecConLib@@AEAAJXZ`
- size: `210`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009260`
- `0x1800092e0`
- `0x1800093c0`
- `0x180009440`
- `0x18000e408`
- `0x18000e83c`
- `0x18000ec68`
- `0x18000ee40`
- `0x18000f298`
- `0x18000f478`
- `0x18000f674`
- `0x18000f908`
- `0x18000fb88`
- `0x18000fd64`

## callees

- `0x18000f1c0`
- `0x18001060c`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000f24c`
- `ole32!CoCreateInstance` at `0x18000f24c`
- `KERNEL32!LeaveCriticalSection` at `0x18000f220`
- `KERNEL32!LeaveCriticalSection` at `0x18000f269`
- `KERNEL32!LeaveCriticalSection` at `0x18000f27e`
- `KERNEL32!LeaveCriticalSection` at `0x18000f220`
- `KERNEL32!LeaveCriticalSection` at `0x18000f269`
- `KERNEL32!LeaveCriticalSection` at `0x18000f27e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSecConLib::InternalInitIfNecessary(CSecConLib *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v4; // eax
  int Instance; // edi
  BOOL v6; // esi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *((_BYTE *)this + 64) )
    return 0;
  v4 = CSafeAutoCriticalSection::Lock((CSecConLib *)((char *)this + 8));
  Instance = v4;
  v6 = v4 == 0;
  if ( v4 > 0 )
    Instance = (unsigned __int16)v4 | 0x80070000;
  if ( Instance >= 0 )
  {
    if ( !*((_BYTE *)this + 64) )
    {
      Instance = CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x17u, &IID_IMSAdminBase_W, (LPVOID *)this + 7);
      *((_BYTE *)this + 64) = Instance >= 0;
    }
    if ( v6 && LODWORD(v2[1].DebugInfo) == 1 )
      LeaveCriticalSection(v2);
  }
  else if ( !v4 && LODWORD(v2[1].DebugInfo) == 1 )
  {
    LeaveCriticalSection(v2);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f1c0  push    rbx
0x18000f1c2  push    rbp
0x18000f1c3  push    rsi
0x18000f1c4  push    rdi
0x18000f1c5  push    r14
0x18000f1c7  sub     rsp, 40h
0x18000f1cb  mov     rbp, rcx
0x18000f1ce  xor     esi, esi
0x18000f1d0  mov     [rsp+68h+var_38], esi
0x18000f1d4  lea     rbx, [rcx+8]
0x18000f1d8  mov     [rsp+68h+var_30], rbx
0x18000f1dd  cmp     [rcx+40h], sil
0x18000f1e1  jz      short loc_18000F1EA
0x18000f1e3  xor     eax, eax
0x18000f1e5  jmp     loc_18000F287
0x18000f1ea  mov     rcx, rbx; this
0x18000f1ed  call    ?Lock@CSafeAutoCriticalSection@@QEAAKXZ; CSafeAutoCriticalSection::Lock(void)
0x18000f1f2  mov     edi, eax
0x18000f1f4  mov     r14d, 1
0x18000f1fa  test    eax, eax
0x18000f1fc  cmovz   esi, r14d
0x18000f200  mov     [rsp+68h+var_38], esi
0x18000f204  jle     short loc_18000F20F
0x18000f206  movzx   edi, ax
0x18000f209  or      edi, 80070000h
0x18000f20f  test    edi, edi
0x18000f211  jns     short loc_18000F229
0x18000f213  test    esi, esi
0x18000f215  jz      short loc_18000F227
0x18000f217  cmp     [rbx+28h], r14d
0x18000f21b  jnz     short loc_18000F227
0x18000f21d  mov     rcx, rbx; lpCriticalSection
0x18000f220  call    cs:__imp_LeaveCriticalSection
0x18000f226  nop
0x18000f227  jmp     short loc_18000F285
0x18000f229  cmp     byte ptr [rbp+40h], 0
0x18000f22d  jnz     short loc_18000F25C
0x18000f22f  lea     rax, [rbp+38h]
0x18000f233  mov     [rsp+68h+ppv], rax; ppv
0x18000f238  lea     r9, IID_IMSAdminBase_W; riid
0x18000f23f  xor     edx, edx; pUnkOuter
0x18000f241  lea     r8d, [rdx+17h]; dwClsContext
0x18000f245  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x18000f24c  call    cs:__imp_CoCreateInstance
0x18000f252  mov     edi, eax
0x18000f254  test    eax, eax
0x18000f256  setns   cl
0x18000f259  mov     [rbp+40h], cl
0x18000f25c  test    esi, esi
0x18000f25e  jz      short loc_18000F271
0x18000f260  cmp     [rbx+28h], r14d
0x18000f264  jnz     short loc_18000F26F
0x18000f266  mov     rcx, rbx; lpCriticalSection
0x18000f269  call    cs:__imp_LeaveCriticalSection
0x18000f26f  xor     esi, esi
0x18000f271  test    esi, esi
0x18000f273  jz      short loc_18000F285
0x18000f275  cmp     [rbx+28h], r14d
0x18000f279  jnz     short loc_18000F285
0x18000f27b  mov     rcx, rbx; lpCriticalSection
0x18000f27e  call    cs:__imp_LeaveCriticalSection
0x18000f284  nop
0x18000f285  mov     eax, edi
0x18000f287  add     rsp, 40h
0x18000f28b  pop     r14
0x18000f28d  pop     rdi
0x18000f28e  pop     rsi
0x18000f28f  pop     rbp
0x18000f290  pop     rbx
0x18000f291  retn
```
