# InternetCrackUrlImpl(ushort const *,ulong,ulong,int *,URL_COMPONENTSW *)

- ea: `0x180044400`
- end: `0x1800444dd`
- name: `?InternetCrackUrlImpl@@YAJPEBGKKPEAHPEAUURL_COMPONENTSW@@@Z`
- size: `221`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpszUrl@<rcx>, DWORD dwUrlLength@<edx>, unsigned int@<r8d>, int *@<r9>, struct URL_COMPONENTSW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800446ac`

## callees

- `0x180013870`
- `0x180044400`
- `0x18007e6ca`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044475`
- `KERNEL32!GetLastError` at `0x18004449d`
- `KERNEL32!GetLastError` at `0x180044475`
- `KERNEL32!GetLastError` at `0x18004449d`
- `WININET!InternetCrackUrlW` at `0x18004445d`
- `WININET!InternetCrackUrlW` at `0x18004445d`

## pseudocode

```c

```
