# FreeEapCredStructure(_EapCredThreadArgs *)

- ea: `0x18001124c`
- end: `0x1800112c2`
- name: `?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z`
- size: `118`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003530`
- `0x180006c60`

## callees

- `0x18001124c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001127f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001128e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001129d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800112b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001127f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001128e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001129d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800112b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800112ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800112ad`

## pseudocode

```c
void __fastcall FreeEapCredStructure(_QWORD *hMem)
{
  _BYTE *v1; // rax
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  if ( hMem )
  {
    v1 = (_BYTE *)hMem[2];
    if ( v1 && *((_DWORD *)hMem + 6) )
    {
      v3 = *((unsigned int *)hMem + 6);
      do
      {
        *v1++ = 0;
        --v3;
      }
      while ( v3 );
    }
    if ( *hMem )
      LocalFree((HLOCAL)*hMem);
    v4 = (void *)hMem[1];
    if ( v4 )
      LocalFree(v4);
    v5 = (void *)hMem[2];
    if ( v5 )
      LocalFree(v5);
    v6 = (void *)hMem[4];
    if ( v6 != (void *)-1LL )
      CloseHandle(v6);
    LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x18001124c  test    rcx, rcx
0x18001124f  jz      short locret_1800112C1
0x180011251  push    rbx
0x180011252  sub     rsp, 20h
0x180011256  mov     rax, [rcx+10h]
0x18001125a  mov     rbx, rcx
0x18001125d  test    rax, rax
0x180011260  jz      short loc_180011277
0x180011262  cmp     dword ptr [rcx+18h], 0
0x180011266  jz      short loc_180011277
0x180011268  mov     ecx, [rcx+18h]
0x18001126b  mov     byte ptr [rax], 0
0x18001126e  inc     rax
0x180011271  sub     rcx, 1
0x180011275  jnz     short loc_18001126B
0x180011277  mov     rcx, [rbx]; hMem
0x18001127a  test    rcx, rcx
0x18001127d  jz      short loc_180011285
0x18001127f  call    cs:__imp_LocalFree
0x180011285  mov     rcx, [rbx+8]; hMem
0x180011289  test    rcx, rcx
0x18001128c  jz      short loc_180011294
0x18001128e  call    cs:__imp_LocalFree
0x180011294  mov     rcx, [rbx+10h]; hMem
0x180011298  test    rcx, rcx
0x18001129b  jz      short loc_1800112A3
0x18001129d  call    cs:__imp_LocalFree
0x1800112a3  mov     rcx, [rbx+20h]; hObject
0x1800112a7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800112ab  jz      short loc_1800112B3
0x1800112ad  call    cs:__imp_CloseHandle
0x1800112b3  mov     rcx, rbx; hMem
0x1800112b6  call    cs:__imp_LocalFree
0x1800112bc  add     rsp, 20h
0x1800112c0  pop     rbx
0x1800112c1  retn
```
