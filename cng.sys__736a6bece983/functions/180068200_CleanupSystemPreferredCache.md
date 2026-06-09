# CleanupSystemPreferredCache

- ea: `0x180068200`
- end: `0x1800682a7`
- name: `CleanupSystemPreferredCache`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800682b0`

## callees

- `0x1800023e0`
- `0x180006470`
- `0x180068200`
- `0x18006ce00`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x18006827d`
- `ntoskrnl!ExDeleteResourceLite` at `0x18006827d`

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
  if ( qword_1800CD7D8 )
  {
    BCryptCloseAlgorithmProvider(qword_1800CD7D8, 0);
    qword_1800CD7D8 = 0;
  }
  if ( dword_1800CD7D0 )
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
    dword_1800CD7D0 = 0;
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
0x180068200  push    rbx
0x180068202  sub     rsp, 20h
0x180068206  mov     rcx, cs:hAlgorithm; hAlgorithm
0x18006820d  test    rcx, rcx
0x180068210  jz      short loc_180068224
0x180068212  xor     edx, edx; dwFlags
0x180068214  call    BCryptCloseAlgorithmProvider
0x180068219  mov     cs:hAlgorithm, 0
0x180068224  mov     rcx, cs:qword_1800CD7D8; hAlgorithm
0x18006822b  test    rcx, rcx
0x18006822e  jz      short loc_180068242
0x180068230  xor     edx, edx; dwFlags
0x180068232  call    BCryptCloseAlgorithmProvider
0x180068237  mov     cs:qword_1800CD7D8, 0
0x180068242  cmp     cs:dword_1800CD7D0, 0
0x180068249  jz      short loc_180068271
0x18006824b  lea     rbx, phEvent
0x180068252  mov     rcx, rbx; hEvent
0x180068255  call    BCryptUnregisterConfigChangeNotify
0x18006825a  mov     eax, 18h
0x18006825f  mov     byte ptr [rbx], 0
0x180068262  inc     rbx
0x180068265  sub     rax, 1
0x180068269  jnz     short loc_18006825F
0x18006826b  mov     cs:dword_1800CD7D0, eax
0x180068271  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180068278  test    rcx, rcx
0x18006827b  jz      short loc_1800682A0
0x18006827d  call    cs:__imp_ExDeleteResourceLite
0x180068284  nop     dword ptr [rax+rax+00h]
0x180068289  mov     rcx, cs:g_pCachedRngRWLock; P
0x180068290  call    MSCryptFree
0x180068295  mov     cs:g_pCachedRngRWLock, 0
0x1800682a0  add     rsp, 20h
0x1800682a4  pop     rbx
0x1800682a5  retn
```
