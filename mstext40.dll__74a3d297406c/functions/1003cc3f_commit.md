# __commit

- ea: `0x1003cc3f`
- end: `0x1003cd28`
- name: `__commit`
- size: `233`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1003ba47`

## callees

- `0x1002d6a8`
- `0x1002d6dc`
- `0x10030870`
- `0x10034c80`
- `0x10034cc5`
- `0x1003bbde`
- `0x1003bcf2`
- `0x1003bd59`
- `0x1003cc3f`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1003ccca`
- `KERNEL32!GetLastError` at `0x1003ccca`
- `KERNEL32!FlushFileBuffers` at `0x1003ccc0`
- `KERNEL32!FlushFileBuffers` at `0x1003ccc0`

## pseudocode

```c
int __cdecl _commit(int FileHandle)
{
  DWORD LastError; // esi
  int v2; // ebx
  void *osfhandle; // eax

  LastError = 0;
  if ( FileHandle != -2 )
  {
    if ( FileHandle < 0
      || FileHandle >= (unsigned int)_nhandle
      || (v2 = (FileHandle & 0x1F) << 6, (*(_BYTE *)(v2 + __pioinfo[FileHandle >> 5] + 4) & 1) == 0) )
    {
      *_errno() = 9;
      _invalid_parameter_noinfo();
      return -1;
    }
    __lock_fhandle(FileHandle);
    if ( (*(_BYTE *)(v2 + __pioinfo[FileHandle >> 5] + 4) & 1) != 0 )
    {
      osfhandle = (void *)_get_osfhandle(FileHandle);
      if ( !FlushFileBuffers(osfhandle) )
        LastError = GetLastError();
      if ( !LastError )
        goto $good$21;
      *__doserrno() = LastError;
    }
    *_errno() = 9;
    LastError = -1;
$good$21:
    _unlock_fhandle(FileHandle);
    return LastError;
  }
  *_errno() = 9;
  return -1;
}

```

## disassembly

```asm
0x1003cc3f  push    14h
0x1003cc41  push    offset stru_1003D228
0x1003cc46  call    __SEH_prolog4
0x1003cc4b  xor     esi, esi
0x1003cc4d  mov     [ebp+var_1C], esi
0x1003cc50  mov     edi, [ebp+FileHandle]
0x1003cc53  cmp     edi, 0FFFFFFFEh
0x1003cc56  jnz     short loc_1003CC68
0x1003cc58  call    __errno
0x1003cc5d  mov     dword ptr [eax], 9
0x1003cc63  jmp     loc_1003CD1F
0x1003cc68  test    edi, edi
0x1003cc6a  js      loc_1003CD0F
0x1003cc70  cmp     edi, __nhandle
0x1003cc76  jnb     loc_1003CD0F
0x1003cc7c  mov     eax, edi
0x1003cc7e  sar     eax, 5
0x1003cc81  mov     [ebp+var_20], eax
0x1003cc84  mov     ebx, edi
0x1003cc86  and     ebx, 1Fh
0x1003cc89  shl     ebx, 6
0x1003cc8c  mov     eax, ___pioinfo[eax*4]
0x1003cc93  movsx   eax, byte ptr [ebx+eax+4]
0x1003cc98  and     eax, 1
0x1003cc9b  jz      short loc_1003CD0F
0x1003cc9d  push    edi
0x1003cc9e  call    ___lock_fhandle
0x1003cca3  pop     ecx
0x1003cca4  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1003cca7  mov     eax, [ebp+var_20]
0x1003ccaa  mov     eax, ___pioinfo[eax*4]
0x1003ccb1  test    byte ptr [ebx+eax+4], 1
0x1003ccb6  jz      short loc_1003CCE0
0x1003ccb8  push    edi; FileHandle
0x1003ccb9  call    __get_osfhandle
0x1003ccbe  pop     ecx
0x1003ccbf  push    eax; hFile
0x1003ccc0  call    ds:__imp__FlushFileBuffers@4
0x1003ccc6  test    eax, eax
0x1003ccc8  jnz     short loc_1003CCD2
0x1003ccca  call    ds:__imp__GetLastError@0
0x1003ccd0  mov     esi, eax
0x1003ccd2  mov     [ebp+var_1C], esi
0x1003ccd5  test    esi, esi
0x1003ccd7  jz      short $good$21
0x1003ccd9  call    ___doserrno
0x1003ccde  mov     [eax], esi
0x1003cce0  call    __errno
0x1003cce5  mov     dword ptr [eax], 9
0x1003cceb  or      esi, 0FFFFFFFFh
0x1003ccee  mov     [ebp+var_1C], esi
0x1003ccf1  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003ccf8  call    loc_1003CD07
0x1003ccfd  mov     eax, esi
0x1003ccff  jmp     short loc_1003CD22
0x1003cd01  mov     edi, [ebp+FileHandle]
0x1003cd04  mov     esi, [ebp+var_1C]
0x1003cd07  push    edi
0x1003cd08  call    __unlock_fhandle
0x1003cd0d  pop     ecx
0x1003cd0e  retn
0x1003cd0f  call    __errno
0x1003cd14  mov     dword ptr [eax], 9
0x1003cd1a  call    __invalid_parameter_noinfo
0x1003cd1f  or      eax, 0FFFFFFFFh
0x1003cd22  call    __SEH_epilog4
0x1003cd27  retn
```
