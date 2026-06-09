# NetDownloadToLocal(x,x,x,x,x)

- ea: `0x100234fb`
- end: `0x1002355d`
- name: `_NetDownloadToLocal@20`
- size: `98`
- prototype: `int __thiscall(wchar_t *FullPath, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x10026c60`

## callees

- `0x10022628`
- `0x10022838`
- `0x10022920`
- `0x100232c9`
- `0x100234fb`

## pseudocode

```c
int __thiscall NetDownloadToLocal(wchar_t *FullPath, _WORD *a2, WCHAR *a3, int a4)
{
  int v5; // ecx
  int v6; // esi

  v6 = ProtocolPrefix();
  *a3 = 0;
  if ( !dword_1003AE18 && !NetInitializeInternetServices() )
    return -20163;
  if ( !v6 )
    return HTTPDownloadFile(FullPath, a2, a3, v5);
  if ( v6 == 1 )
    return FTPDownloadFiles(FullPath, a2, a3, v5);
  return -1023;
}

```

## disassembly

```asm
0x100234fb  mov     edi, edi
0x100234fd  push    ebp
0x100234fe  mov     ebp, esp
0x10023500  push    ebx
0x10023501  push    esi
0x10023502  push    edi
0x10023503  mov     edi, ecx
0x10023505  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x1002350a  mov     ebx, [ebp+arg_4]
0x1002350d  mov     esi, eax
0x1002350f  xor     eax, eax
0x10023511  mov     [ebx], ax
0x10023514  cmp     dword_1003AE18, eax
0x1002351a  jnz     short loc_1002352C
0x1002351c  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x10023521  test    eax, eax
0x10023523  jnz     short loc_1002352C
0x10023525  mov     eax, 0FFFFB13Dh
0x1002352a  jmp     short loc_10023556
0x1002352c  test    esi, esi
0x1002352e  jnz     short loc_1002353E
0x10023530  mov     edx, [ebp+arg_0]
0x10023533  push    ecx; int
0x10023534  push    ebx; int
0x10023535  mov     ecx, edi; FullPath
0x10023537  call    HTTPDownloadFile
0x1002353c  jmp     short loc_10023556
0x1002353e  cmp     esi, 1
0x10023541  jnz     short loc_10023551
0x10023543  push    ecx; int
0x10023544  push    ebx; int
0x10023545  push    [ebp+arg_0]; int
0x10023548  mov     ecx, edi; FullPath
0x1002354a  call    FTPDownloadFiles
0x1002354f  jmp     short loc_10023556
0x10023551  mov     eax, 0FFFFFC01h
0x10023556  pop     edi
0x10023557  pop     esi
0x10023558  pop     ebx
0x10023559  pop     ebp
0x1002355a  retn    0Ch
```
