# SqmHelper::LogSqmTokenLifetime(ushort const *,ulong,ulong)

- ea: `0x18001182c`
- end: `0x18001190b`
- name: `?LogSqmTokenLifetime@SqmHelper@@YAXPEBGKK@Z`
- size: `223`
- prototype: `void __fastcall(SqmHelper *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000e020`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800117c4`
- `0x18001182c`
- `0x18001ac64`
- `0x18001b340`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x1800118c1`
- `ntdll!WinSqmAddToStreamEx` at `0x1800118c1`

## string_xrefs

- `0x1800118ce`: `SqmDssTokenLifetime failed. No SQM session active!`
- `0x1800118db`: `SqmHelper::LogSqmTokenLifetime`

## pseudocode

```c
void __fastcall SqmHelper::LogSqmTokenLifetime(SqmHelper *this, const unsigned __int16 *a2, int a3)
{
  int v4; // esi
  __int64 v6; // rcx
  __int64 v7; // r8
  int *v8; // rax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v10[12]; // [rsp+38h] [rbp-38h] BYREF

  v4 = (int)a2;
  if ( SqmHelper::GetGlobalSession(this) )
  {
    v9 = 0;
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)this + v7) );
    v10[2] = Crc32::crc((Crc32 *)&v9, this, 2 * v7);
    v10[0] = 16;
    v10[4] = 16;
    v10[8] = 16;
    v10[6] = v4;
    v10[1] = 1;
    v10[5] = 1;
    v10[9] = 1;
    v10[10] = a3;
    WinSqmAddToStreamEx(*(_QWORD *)&g_hDssSqmGlobalSession.Data1, 2084, 3, v10, 0);
  }
  else
  {
    v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v6);
    DSLogger::LogError(
      (DSLogger *)v8,
      L"SqmHelper::LogSqmTokenLifetime",
      108,
      L"SqmDssTokenLifetime failed. No SQM session active!");
  }
}

```

## disassembly

```asm
0x18001182c  mov     [rsp-18h+arg_8], rbx
0x180011831  mov     [rsp-18h+arg_10], rsi
0x180011836  push    rbp
0x180011837  push    rdi
0x180011838  push    r14
0x18001183a  mov     rbp, rsp
0x18001183d  sub     rsp, 70h
0x180011841  mov     rax, cs:__security_cookie
0x180011848  xor     rax, rsp
0x18001184b  mov     [rbp+var_8], rax
0x18001184f  mov     edi, r8d
0x180011852  mov     esi, edx
0x180011854  mov     rbx, rcx
0x180011857  call    ?GetGlobalSession@SqmHelper@@YAPEAU_GUID@@XZ; SqmHelper::GetGlobalSession(void)
0x18001185c  xor     r14d, r14d
0x18001185f  test    rax, rax
0x180011862  jz      short loc_1800118C9
0x180011864  mov     [rbp+var_40], r14d
0x180011868  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001186c  inc     r8
0x18001186f  cmp     [rbx+r8*2], r14w
0x180011874  jnz     short loc_18001186C
0x180011876  add     r8, r8; unsigned __int64
0x180011879  lea     rcx, [rbp+var_40]; this
0x18001187d  mov     rdx, rbx; void *
0x180011880  call    ?crc@Crc32@@QEAAIPEBX_K@Z; Crc32::crc(void const *,unsigned __int64)
0x180011885  mov     ecx, 10h
0x18001188a  mov     [rbp+var_30], eax
0x18001188d  mov     [rbp+var_38], ecx
0x180011890  lea     r9, [rbp+var_38]
0x180011894  mov     [rbp+var_28], ecx
0x180011897  mov     edx, 824h
0x18001189c  mov     [rbp+var_18], ecx
0x18001189f  lea     eax, [rcx-0Fh]
0x1800118a2  mov     [rbp+var_20], esi
0x1800118a5  lea     r8d, [rcx-0Dh]
0x1800118a9  mov     [rbp+var_34], eax
0x1800118ac  mov     rcx, qword ptr cs:?g_hDssSqmGlobalSession@@3PEAU_GUID@@EA.Data1; _GUID * g_hDssSqmGlobalSession ...
0x1800118b3  mov     [rbp+var_24], eax
0x1800118b6  mov     [rbp+var_14], eax
0x1800118b9  mov     [rbp+var_10], edi
0x1800118bc  mov     [rsp+70h+var_50], r14d
0x1800118c1  call    cs:__imp_WinSqmAddToStreamEx
0x1800118c7  jmp     short loc_1800118EA
0x1800118c9  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800118ce  lea     r9, aSqmdsstokenlif; "SqmDssTokenLifetime failed. No SQM sess"...
0x1800118d5  mov     r8d, 6Ch ; 'l'; unsigned int
0x1800118db  lea     rdx, aSqmhelperLogsq_0; "SqmHelper::LogSqmTokenLifetime"
0x1800118e2  mov     rcx, rax; this
0x1800118e5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800118ea  mov     rcx, [rbp+var_8]
0x1800118ee  xor     rcx, rsp; StackCookie
0x1800118f1  call    __security_check_cookie
0x1800118f6  lea     r11, [rsp+70h+var_s0]
0x1800118fb  mov     rbx, [r11+28h]
0x1800118ff  mov     rsi, [r11+30h]
0x180011903  mov     rsp, r11
0x180011906  pop     r14
0x180011908  pop     rdi
0x180011909  pop     rbp
0x18001190a  retn
```
