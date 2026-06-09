# FindLatestVersion(ushort * *,int (*)(ushort *,void *))

- ea: `0x180002f30`
- end: `0x180003068`
- name: `?FindLatestVersion@@YAJPEAPEAGP6AHPEAGPEAX@Z@Z`
- size: `312`
- prototype: `__int64 __fastcall(unsigned __int16 **, int (*)(unsigned __int16 *, void *))`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180002a90`

## callees

- `0x180001ff0`
- `0x180002f30`
- `0x180003840`
- `0x180003e00`
- `0x180004ed0`
- `0x180005300`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002f79`
- `KERNEL32!GetLastError` at `0x180002f94`
- `KERNEL32!GetLastError` at `0x180002fe0`
- `KERNEL32!GetLastError` at `0x180002ff5`
- `KERNEL32!GetLastError` at `0x180002f79`
- `KERNEL32!GetLastError` at `0x180002f94`
- `KERNEL32!GetLastError` at `0x180002fe0`
- `KERNEL32!GetLastError` at `0x180002ff5`
- `KERNEL32!SetLastError` at `0x180002fed`
- `KERNEL32!SetLastError` at `0x180003001`
- `KERNEL32!SetLastError` at `0x180002fed`
- `KERNEL32!SetLastError` at `0x180003001`

## string_xrefs

- `0x180002f58`: `InstallRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FindLatestVersion(unsigned __int16 **a1, int (*a2)(unsigned __int16 *, void *))
{
  unsigned __int16 *String; // rax
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  DWORD LastError; // esi
  DWORD v8; // ebx

  String = EnvGetString((wchar_t *)L"Version");
  v4 = String;
  if ( String && !*String )
  {
    operator delete(String);
    v4 = 0;
  }
  v5 = EnvGetString((wchar_t *)L"InstallRoot");
  v6 = v5;
  if ( v5 && !*v5 )
  {
    operator delete(v5);
    v6 = 0;
  }
  if ( v4 && v6 && (unsigned int)CheckShimImplCallback(v4, 0) )
  {
    operator delete(v6);
    *a1 = v4;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( v4 )
      ClrFreeInProcessHeapBootstrap(0, v4);
    if ( LastError && !GetLastError() )
      SetLastError(LastError);
    v8 = GetLastError();
    if ( v6 )
      ClrFreeInProcessHeapBootstrap(0, v6);
    if ( v8 )
    {
      if ( !GetLastError() )
        SetLastError(v8);
    }
    return FindLatestVersionWithCallback(
             a1,
             0,
             0,
             (unsigned int (__fastcall *)(void *, __int64))CheckShimImplCallback,
             0,
             1,
             0);
  }
}

```

## disassembly

```asm
0x180002f30  push    rbx
0x180002f32  push    rbp
0x180002f33  push    rsi
0x180002f34  push    rdi
0x180002f35  push    r14
0x180002f37  sub     rsp, 40h
0x180002f3b  mov     r14, rcx
0x180002f3e  lea     rcx, aVersion_1; "Version"
0x180002f45  call    ?EnvGetString@@YAPEAGPEBG@Z; EnvGetString(ushort const *)
0x180002f4a  mov     rbx, rax
0x180002f4d  xor     ebp, ebp
0x180002f4f  test    rax, rax
0x180002f52  jnz     loc_180003009
0x180002f58  lea     rcx, aInstallroot; "InstallRoot"
0x180002f5f  call    ?EnvGetString@@YAPEAGPEBG@Z; EnvGetString(ushort const *)
0x180002f64  mov     rdi, rax
0x180002f67  test    rax, rax
0x180002f6a  jnz     loc_180003022
0x180002f70  test    rbx, rbx
0x180002f73  jnz     loc_18000303B
0x180002f79  call    cs:__imp_GetLastError
0x180002f7f  mov     esi, eax
0x180002f81  test    rbx, rbx
0x180002f84  jz      short loc_180002F90
0x180002f86  mov     rdx, rbx; void *
0x180002f89  xor     ecx, ecx; unsigned int
0x180002f8b  call    ?ClrFreeInProcessHeapBootstrap@@YAHKPEAX@Z; ClrFreeInProcessHeapBootstrap(ulong,void *)
0x180002f90  test    esi, esi
0x180002f92  jnz     short loc_180002FE0
0x180002f94  call    cs:__imp_GetLastError
0x180002f9a  mov     ebx, eax
0x180002f9c  test    rdi, rdi
0x180002f9f  jz      short loc_180002FAB
0x180002fa1  mov     rdx, rdi; void *
0x180002fa4  xor     ecx, ecx; unsigned int
0x180002fa6  call    ?ClrFreeInProcessHeapBootstrap@@YAHKPEAX@Z; ClrFreeInProcessHeapBootstrap(ulong,void *)
0x180002fab  test    ebx, ebx
0x180002fad  jnz     short loc_180002FF5
0x180002faf  mov     [rsp+68h+var_38], rbp
0x180002fb4  mov     [rsp+68h+var_40], 1
0x180002fbc  mov     [rsp+68h+var_48], rbp
0x180002fc1  lea     r9, ?CheckShimImplCallback@@YAHPEAGPEAX@Z; CheckShimImplCallback(ushort *,void *)
0x180002fc8  xor     r8d, r8d
0x180002fcb  xor     edx, edx
0x180002fcd  mov     rcx, r14
0x180002fd0  call    ?FindLatestVersionWithCallback@@YAJPEAPEAGW4VERSION_ARCHITECTURE@@HP6AHPEAGPEAX@Z3HPEAVShimLog@@@Z; FindLatestVersionWithCallback(ushort * *,VERSION_ARCHITECTURE,int,int (*)(ushort *,void *),void *,int,ShimLog *)
0x180002fd5  add     rsp, 40h
0x180002fd9  pop     r14
0x180002fdb  pop     rdi
0x180002fdc  pop     rsi
0x180002fdd  pop     rbp
0x180002fde  pop     rbx
0x180002fdf  retn
0x180002fe0  call    cs:__imp_GetLastError
0x180002fe6  nop
0x180002fe7  test    eax, eax
0x180002fe9  jnz     short loc_180002F94
0x180002feb  mov     ecx, esi; dwErrCode
0x180002fed  call    cs:__imp_SetLastError
0x180002ff3  jmp     short loc_180002F94
0x180002ff5  call    cs:__imp_GetLastError
0x180002ffb  test    eax, eax
0x180002ffd  jnz     short loc_180002FAF
0x180002fff  mov     ecx, ebx; dwErrCode
0x180003001  call    cs:__imp_SetLastError
0x180003007  jmp     short loc_180002FAF
0x180003009  cmp     [rax], bp
0x18000300c  jnz     loc_180002F58
0x180003012  mov     rcx, rax; void *
0x180003015  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000301a  mov     rbx, rbp
0x18000301d  jmp     loc_180002F58
0x180003022  cmp     [rax], bp
0x180003025  jnz     loc_180002F70
0x18000302b  mov     rcx, rax; void *
0x18000302e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003033  mov     rdi, rbp
0x180003036  jmp     loc_180002F70
0x18000303b  test    rdi, rdi
0x18000303e  jz      loc_180002F79
0x180003044  xor     edx, edx; void *
0x180003046  mov     rcx, rbx; wchar_t *
0x180003049  call    ?CheckShimImplCallback@@YAHPEAGPEAX@Z; CheckShimImplCallback(ushort *,void *)
0x18000304e  test    eax, eax
0x180003050  jz      loc_180002F79
0x180003056  mov     rcx, rdi; void *
0x180003059  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000305e  mov     [r14], rbx
0x180003061  xor     eax, eax
0x180003063  jmp     loc_180002FD5
```
