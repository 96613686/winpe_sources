# CleanupSystemPreferredCache

- ea: `0x180067800`
- end: `0x1800678a7`
- name: `CleanupSystemPreferredCache`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800678b0`

## callees

- `0x1800023e0`
- `0x180006470`
- `0x180067800`
- `0x18006c400`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x18006787d`
- `ntoskrnl!ExDeleteResourceLite` at `0x18006787d`

## pseudocode

```c
void CleanupSystemPreferredCache()
{
  HANDLE *v0; // rbx
  __int64 v1; // rax

  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  if ( qword_1800CB798 )
  {
    BCryptCloseAlgorithmProvider(qword_1800CB798, 0);
    qword_1800CB798 = 0;
  }
  if ( dword_1800CB790 )
  {
    v0 = &phEvent;
    BCryptUnregisterConfigChangeNotify(&phEvent);
    v1 = 24;
    do
    {
      *(_BYTE *)v0 = 0;
      v0 = (HANDLE *)((char *)v0 + 1);
      --v1;
    }
    while ( v1 );
    dword_1800CB790 = 0;
  }
  if ( g_pCachedRngRWLock )
  {
    ExDeleteResourceLite(g_pCachedRngRWLock);
    MSCryptFree(g_pCachedRngRWLock);
    g_pCachedRngRWLock = 0;
  }
}

```

## disassembly

```asm
0x180067800  push    rbx
0x180067802  sub     rsp, 20h
0x180067806  mov     rcx, cs:hAlgorithm; hAlgorithm
0x18006780d  test    rcx, rcx
0x180067810  jz      short loc_180067824
0x180067812  xor     edx, edx; dwFlags
0x180067814  call    BCryptCloseAlgorithmProvider
0x180067819  mov     cs:hAlgorithm, 0
0x180067824  mov     rcx, cs:qword_1800CB798; hAlgorithm
0x18006782b  test    rcx, rcx
0x18006782e  jz      short loc_180067842
0x180067830  xor     edx, edx; dwFlags
0x180067832  call    BCryptCloseAlgorithmProvider
0x180067837  mov     cs:qword_1800CB798, 0
0x180067842  cmp     cs:dword_1800CB790, 0
0x180067849  jz      short loc_180067871
0x18006784b  lea     rbx, phEvent
0x180067852  mov     rcx, rbx; hEvent
0x180067855  call    BCryptUnregisterConfigChangeNotify
0x18006785a  mov     eax, 18h
0x18006785f  mov     byte ptr [rbx], 0
0x180067862  inc     rbx
0x180067865  sub     rax, 1
0x180067869  jnz     short loc_18006785F
0x18006786b  mov     cs:dword_1800CB790, eax
0x180067871  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180067878  test    rcx, rcx
0x18006787b  jz      short loc_1800678A0
0x18006787d  call    cs:__imp_ExDeleteResourceLite
0x180067884  nop     dword ptr [rax+rax+00h]
0x180067889  mov     rcx, cs:g_pCachedRngRWLock; P
0x180067890  call    MSCryptFree
0x180067895  mov     cs:g_pCachedRngRWLock, 0
0x1800678a0  add     rsp, 20h
0x1800678a4  pop     rbx
0x1800678a5  retn
```
