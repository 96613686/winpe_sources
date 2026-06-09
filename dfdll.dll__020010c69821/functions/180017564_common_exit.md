# common_exit

- ea: `0x180017564`
- end: `0x1800176d0`
- name: `common_exit`
- size: `364`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180017790`
- `0x1800177a0`

## callees

- `0x180012bf0`
- `0x1800172f0`
- `0x180017558`
- `0x180017564`
- `0x1800176d0`
- `0x18001771c`
- `0x180018138`
- `0x1800183cc`
- `0x180018bd8`
- `0x180018c38`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001758c`
- `KERNEL32!GetModuleHandleW` at `0x18001758c`

## pseudocode

```c
__int64 __fastcall common_exit(UINT uExitCode, int a2, int a3)
{
  HMODULE ModuleHandleW; // rax
  char *v7; // rcx
  _onexit_table_t *v8; // rcx
  char v9; // al
  __int64 result; // rax

  if ( !a3 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
    {
      if ( *(_WORD *)ModuleHandleW == 23117 )
      {
        v7 = (char *)ModuleHandleW + *((int *)ModuleHandleW + 15);
        if ( *(_DWORD *)v7 == 17744
          && *((_WORD *)v7 + 12) == 523
          && *((_DWORD *)v7 + 33) > 0xEu
          && *((_DWORD *)v7 + 62) != a3 )
        {
          try_cor_exit_process(uExitCode);
        }
      }
    }
  }
  _acrt_lock(2);
  if ( !byte_18002E190 )
  {
    _InterlockedExchange(&dword_18002E180, 1);
    if ( a2 )
    {
      if ( a2 != 1 )
      {
LABEL_17:
        if ( !a2 )
          initterm((_PVFV *)&_xp_a, (_PVFV *)&_xp_z);
        initterm((_PVFV *)&_xt_a, (_PVFV *)&_xt_z);
        v9 = byte_18002E190;
        if ( !a3 )
          v9 = 1;
        byte_18002E190 = v9;
        goto LABEL_22;
      }
      v8 = &_acrt_at_quick_exit_table;
    }
    else
    {
      if ( qword_18002E188 != (_security_cookie ^ __ROR8__(0, 64 - ((unsigned __int8)_security_cookie & 0x3Fu))) )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))__ROR8__(
                                                        qword_18002E188 ^ _security_cookie,
                                                        _security_cookie & 0x3F))(
          0,
          0,
          0);
      v8 = &_acrt_atexit_table;
    }
    execute_onexit_table(v8);
    goto LABEL_17;
  }
LABEL_22:
  result = _acrt_unlock(2);
  if ( !a3 )
    exit_or_terminate_process(uExitCode);
  return result;
}

```

## disassembly

```asm
0x180017564  mov     rax, rsp
0x180017567  mov     [rax+8], rbx
0x18001756b  mov     [rax+10h], rsi
0x18001756f  mov     [rax+18h], rdi
0x180017573  mov     [rax+20h], r14
0x180017577  push    r15
0x180017579  sub     rsp, 20h
0x18001757d  mov     esi, r8d
0x180017580  mov     ebx, edx
0x180017582  mov     r14d, ecx
0x180017585  test    r8d, r8d
0x180017588  jnz     short loc_1800175D4
0x18001758a  xor     ecx, ecx; lpModuleName
0x18001758c  call    cs:__imp_GetModuleHandleW
0x180017592  test    rax, rax
0x180017595  jz      short loc_1800175D4
0x180017597  mov     ecx, 5A4Dh
0x18001759c  cmp     [rax], cx
0x18001759f  jnz     short loc_1800175D4
0x1800175a1  movsxd  rcx, dword ptr [rax+3Ch]
0x1800175a5  add     rcx, rax
0x1800175a8  cmp     dword ptr [rcx], 4550h
0x1800175ae  jnz     short loc_1800175D4
0x1800175b0  mov     eax, 20Bh
0x1800175b5  cmp     [rcx+18h], ax
0x1800175b9  jnz     short loc_1800175D4
0x1800175bb  cmp     dword ptr [rcx+84h], 0Eh
0x1800175c2  jbe     short loc_1800175D4
0x1800175c4  cmp     [rcx+0F8h], esi
0x1800175ca  jz      short loc_1800175D4
0x1800175cc  mov     ecx, r14d
0x1800175cf  call    try_cor_exit_process
0x1800175d4  mov     ecx, 2
0x1800175d9  call    __acrt_lock
0x1800175de  nop
0x1800175df  cmp     cs:byte_18002E190, 0
0x1800175e6  jnz     loc_18001769E
0x1800175ec  mov     r15d, 1
0x1800175f2  mov     eax, r15d
0x1800175f5  xchg    eax, cs:dword_18002E180
0x1800175fb  test    ebx, ebx
0x1800175fd  jnz     short loc_180017647
0x1800175ff  mov     rdi, cs:__security_cookie
0x180017606  mov     edx, edi
0x180017608  and     edx, 3Fh
0x18001760b  lea     ecx, [rbx+40h]
0x18001760e  sub     ecx, edx
0x180017610  xor     eax, eax
0x180017612  ror     rax, cl
0x180017615  xor     rax, rdi
0x180017618  mov     rcx, cs:qword_18002E188
0x18001761f  cmp     rcx, rax
0x180017622  jz      short loc_18001763E
0x180017624  xor     rdi, rcx
0x180017627  mov     ecx, edx
0x180017629  ror     rdi, cl
0x18001762c  mov     rcx, rdi
0x18001762f  call    cs:__guard_check_icall_fptr
0x180017635  xor     r8d, r8d
0x180017638  xor     edx, edx
0x18001763a  xor     ecx, ecx
0x18001763c  call    rdi
0x18001763e  lea     rcx, __acrt_atexit_table
0x180017645  jmp     short loc_180017653
0x180017647  cmp     ebx, r15d
0x18001764a  jnz     short loc_180017659
0x18001764c  lea     rcx, __acrt_at_quick_exit_table; Table
0x180017653  call    _execute_onexit_table
0x180017658  nop
0x180017659  test    ebx, ebx
0x18001765b  jnz     short loc_180017670
0x18001765d  lea     rdx, __xp_z; Last
0x180017664  lea     rcx, __xp_a; First
0x18001766b  call    _initterm
0x180017670  lea     rdx, __xt_z; Last
0x180017677  lea     rcx, __xt_a; First
0x18001767e  call    _initterm
0x180017683  movzx   eax, cs:byte_18002E190
0x18001768a  test    esi, esi
0x18001768c  cmovz   eax, r15d
0x180017690  mov     cs:byte_18002E190, al
0x180017696  jmp     short loc_18001769E
0x180017698  call    terminate
0x18001769e  mov     ecx, 2
0x1800176a3  call    __acrt_unlock
0x1800176a8  test    esi, esi
0x1800176aa  jnz     short loc_1800176B5
0x1800176ac  mov     ecx, r14d; uExitCode
0x1800176af  call    exit_or_terminate_process
0x1800176b5  mov     rbx, [rsp+28h+arg_0]
0x1800176ba  mov     rsi, [rsp+28h+arg_8]
0x1800176bf  mov     rdi, [rsp+28h+arg_10]
0x1800176c4  mov     r14, [rsp+28h+arg_18]
0x1800176c9  add     rsp, 20h
0x1800176cd  pop     r15
0x1800176cf  retn
0x18001f70a  push    rbp
0x18001f70c  sub     rsp, 20h
0x18001f710  mov     rbp, rdx
0x18001f713  mov     rax, [rcx]
0x18001f716  mov     ecx, [rax]
0x18001f718  call    atexit_exception_filter
0x18001f71d  nop
0x18001f71e  add     rsp, 20h
0x18001f722  pop     rbp
0x18001f723  retn
0x18001f725  push    rbp
0x18001f727  sub     rsp, 20h
0x18001f72b  mov     rbp, rdx
0x18001f72e  mov     ecx, 2
0x18001f733  add     rsp, 20h
0x18001f737  pop     rbp
0x18001f738  jmp     __acrt_unlock
```
