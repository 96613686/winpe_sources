# NetDownloadToLocal(x,x,x,x,x)

- ea: `0x1000d720`
- end: `0x1000d796`
- name: `_NetDownloadToLocal@20`
- size: `118`
- prototype: `int __stdcall(wchar_t *FullPath, int, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR, size_t cchDest)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1000ff30`
- `0x10011d90`

## callees

- `0x1000c370`
- `0x1000cbf0`
- `0x1000d720`
- `0x1000ddd0`
- `0x1000e900`

## pseudocode

```c
int __stdcall NetDownloadToLocal(
        wchar_t *FullPath,
        void *a2,
        STRSAFE_LPCWSTR pszSrc,
        STRSAFE_LPWSTR a4,
        size_t cchDest)
{
  int v5; // esi

  v5 = ProtocolPrefix(FullPath);
  *a4 = 0;
  if ( !dword_10040FB8 && !NetInitializeInternetServices() )
    return -20163;
  if ( !v5 )
    return HTTPDownloadFile(FullPath, pszSrc, a4, cchDest);
  if ( v5 == 1 )
    return FTPDownloadFiles(FullPath, a2, (int)pszSrc, a4, cchDest);
  return -1023;
}

```

## disassembly

```asm
0x1000d720  push    ebx
0x1000d721  push    esi
0x1000d722  push    edi
0x1000d723  mov     edi, [esp+0Ch+FullPath]
0x1000d727  push    edi
0x1000d728  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x1000d72d  mov     ebx, [esp+0Ch+arg_C]
0x1000d731  mov     esi, eax
0x1000d733  xor     eax, eax
0x1000d735  mov     [ebx], ax
0x1000d738  cmp     dword_10040FB8, eax
0x1000d73e  jnz     short loc_1000D754
0x1000d740  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x1000d745  test    eax, eax
0x1000d747  jnz     short loc_1000D754
0x1000d749  pop     edi
0x1000d74a  pop     esi
0x1000d74b  mov     eax, 0FFFFB13Dh
0x1000d750  pop     ebx
0x1000d751  retn    14h
0x1000d754  test    esi, esi
0x1000d756  jnz     short loc_1000D76D
0x1000d758  push    [esp+0Ch+cchDest]; cchDest
0x1000d75c  push    ebx; int
0x1000d75d  push    [esp+14h+pszSrc]; pszSrc
0x1000d761  push    edi; FullPath
0x1000d762  call    HTTPDownloadFile
0x1000d767  pop     edi
0x1000d768  pop     esi
0x1000d769  pop     ebx
0x1000d76a  retn    14h
0x1000d76d  cmp     esi, 1
0x1000d770  jnz     short loc_1000D78B
0x1000d772  push    [esp+0Ch+cchDest]; cchDest
0x1000d776  push    ebx; STRSAFE_LPWSTR
0x1000d777  push    [esp+14h+pszSrc]; int
0x1000d77b  push    [esp+18h+arg_4]; int
0x1000d77f  push    edi; FullPath
0x1000d780  call    FTPDownloadFiles
0x1000d785  pop     edi
0x1000d786  pop     esi
0x1000d787  pop     ebx
0x1000d788  retn    14h
0x1000d78b  pop     edi
0x1000d78c  pop     esi
0x1000d78d  mov     eax, 0FFFFFC01h
0x1000d792  pop     ebx
0x1000d793  retn    14h
```
