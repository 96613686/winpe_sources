# SqmHelper::LogSqmTokenUsage(ushort const *,ulong,ulong)

- ea: `0x180011914`
- end: `0x1800119d8`
- name: `?LogSqmTokenUsage@SqmHelper@@YAXPEBGKK@Z`
- size: `196`
- prototype: `void __fastcall(SqmHelper *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000f740`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800117c4`
- `0x180011914`
- `0x18001ac64`
- `0x18001b340`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18001199a`
- `ntdll!WinSqmAddToStreamEx` at `0x18001199a`

## string_xrefs

- `0x1800119a7`: `SqmDssAppTokenUsage failed. No SQM session active!`
- `0x1800119b4`: `SqmHelper::LogSqmTokenUsage`

## pseudocode

```c
void __fastcall SqmHelper::LogSqmTokenUsage(SqmHelper *this, const unsigned __int16 *a2)
{
  int v2; // edi
  __int64 v4; // rcx
  __int64 v5; // r8
  int *v6; // rax
  int v7; // [rsp+30h] [rbp-48h] BYREF
  _DWORD v8[12]; // [rsp+38h] [rbp-40h] BYREF

  v2 = (int)a2;
  if ( SqmHelper::GetGlobalSession(this) )
  {
    v7 = 0;
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)this + v5) );
    v8[2] = Crc32::crc((Crc32 *)&v7, this, 2 * v5);
    v8[0] = 16;
    v8[4] = 16;
    v8[8] = 16;
    v8[6] = v2;
    v8[1] = 1;
    v8[5] = 1;
    v8[10] = 1;
    v8[9] = 1;
    WinSqmAddToStreamEx(*(_QWORD *)&g_hDssSqmGlobalSession.Data1, 2083, 3, v8, 0);
  }
  else
  {
    v6 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v4);
    DSLogger::LogError(
      (DSLogger *)v6,
      L"SqmHelper::LogSqmTokenUsage",
      87,
      L"SqmDssAppTokenUsage failed. No SQM session active!");
  }
}

```

## disassembly

```asm
0x180011914  push    rbp
0x180011916  push    rbx
0x180011917  push    rsi
0x180011918  push    rdi
0x180011919  mov     rbp, rsp
0x18001191c  sub     rsp, 78h
0x180011920  mov     rax, cs:__security_cookie
0x180011927  xor     rax, rsp
0x18001192a  mov     [rbp+var_10], rax
0x18001192e  mov     edi, edx
0x180011930  mov     rbx, rcx
0x180011933  call    ?GetGlobalSession@SqmHelper@@YAPEAU_GUID@@XZ; SqmHelper::GetGlobalSession(void)
0x180011938  xor     esi, esi
0x18001193a  test    rax, rax
0x18001193d  jz      short loc_1800119A2
0x18001193f  mov     [rbp+var_48], esi
0x180011942  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011946  inc     r8
0x180011949  cmp     [rbx+r8*2], si
0x18001194e  jnz     short loc_180011946
0x180011950  add     r8, r8; unsigned __int64
0x180011953  lea     rcx, [rbp+var_48]; this
0x180011957  mov     rdx, rbx; void *
0x18001195a  call    ?crc@Crc32@@QEAAIPEBX_K@Z; Crc32::crc(void const *,unsigned __int64)
0x18001195f  mov     ecx, 10h
0x180011964  mov     [rbp+var_38], eax
0x180011967  mov     [rbp+var_40], ecx
0x18001196a  lea     r9, [rbp+var_40]
0x18001196e  mov     [rbp+var_30], ecx
0x180011971  mov     edx, 823h
0x180011976  mov     [rbp+var_20], ecx
0x180011979  lea     eax, [rcx-0Fh]
0x18001197c  mov     [rbp+var_28], edi
0x18001197f  lea     r8d, [rcx-0Dh]
0x180011983  mov     [rbp+var_3C], eax
0x180011986  mov     rcx, qword ptr cs:?g_hDssSqmGlobalSession@@3PEAU_GUID@@EA.Data1; _GUID * g_hDssSqmGlobalSession ...
0x18001198d  mov     [rbp+var_2C], eax
0x180011990  mov     [rbp+var_18], eax
0x180011993  mov     [rbp+var_1C], eax
0x180011996  mov     [rsp+78h+var_58], esi
0x18001199a  call    cs:__imp_WinSqmAddToStreamEx
0x1800119a0  jmp     short loc_1800119C3
0x1800119a2  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800119a7  lea     r9, aSqmdssapptoken; "SqmDssAppTokenUsage failed. No SQM sess"...
0x1800119ae  mov     r8d, 57h ; 'W'; unsigned int
0x1800119b4  lea     rdx, aSqmhelperLogsq; "SqmHelper::LogSqmTokenUsage"
0x1800119bb  mov     rcx, rax; this
0x1800119be  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800119c3  mov     rcx, [rbp+var_10]
0x1800119c7  xor     rcx, rsp; StackCookie
0x1800119ca  call    __security_check_cookie
0x1800119cf  add     rsp, 78h
0x1800119d3  pop     rdi
0x1800119d4  pop     rsi
0x1800119d5  pop     rbx
0x1800119d6  pop     rbp
0x1800119d7  retn
```
