# CleanupSystemPreferredCache

- ea: `0x1800719a0`
- end: `0x180071a47`
- name: `CleanupSystemPreferredCache`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180071a50`

## callees

- `0x18000c500`
- `0x180010590`
- `0x1800719a0`
- `0x1800765a0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180071a1d`
- `ntoskrnl!ExDeleteResourceLite` at `0x180071a1d`

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
  if ( qword_1800D37D8 )
  {
    BCryptCloseAlgorithmProvider(qword_1800D37D8, 0);
    qword_1800D37D8 = 0;
  }
  if ( dword_1800D37D0 )
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
    dword_1800D37D0 = 0;
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
0x1800719a0  push    rbx
0x1800719a2  sub     rsp, 20h
0x1800719a6  mov     rcx, cs:hAlgorithm; hAlgorithm
0x1800719ad  test    rcx, rcx
0x1800719b0  jz      short loc_1800719C4
0x1800719b2  xor     edx, edx; dwFlags
0x1800719b4  call    BCryptCloseAlgorithmProvider
0x1800719b9  mov     cs:hAlgorithm, 0
0x1800719c4  mov     rcx, cs:qword_1800D37D8; hAlgorithm
0x1800719cb  test    rcx, rcx
0x1800719ce  jz      short loc_1800719E2
0x1800719d0  xor     edx, edx; dwFlags
0x1800719d2  call    BCryptCloseAlgorithmProvider
0x1800719d7  mov     cs:qword_1800D37D8, 0
0x1800719e2  cmp     cs:dword_1800D37D0, 0
0x1800719e9  jz      short loc_180071A11
0x1800719eb  lea     rbx, phEvent
0x1800719f2  mov     rcx, rbx; hEvent
0x1800719f5  call    BCryptUnregisterConfigChangeNotify
0x1800719fa  mov     eax, 18h
0x1800719ff  mov     byte ptr [rbx], 0
0x180071a02  inc     rbx
0x180071a05  sub     rax, 1
0x180071a09  jnz     short loc_1800719FF
0x180071a0b  mov     cs:dword_1800D37D0, eax
0x180071a11  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180071a18  test    rcx, rcx
0x180071a1b  jz      short loc_180071A40
0x180071a1d  call    cs:__imp_ExDeleteResourceLite
0x180071a24  nop     dword ptr [rax+rax+00h]
0x180071a29  mov     rcx, cs:g_pCachedRngRWLock; P
0x180071a30  call    MSCryptFree
0x180071a35  mov     cs:g_pCachedRngRWLock, 0
0x180071a40  add     rsp, 20h
0x180071a44  pop     rbx
0x180071a45  retn
```
