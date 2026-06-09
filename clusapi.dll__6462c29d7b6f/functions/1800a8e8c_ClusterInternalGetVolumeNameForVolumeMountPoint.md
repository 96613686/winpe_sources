# ClusterInternalGetVolumeNameForVolumeMountPoint

- ea: `0x1800a8e8c`
- end: `0x1800a8f3e`
- name: `ClusterInternalGetVolumeNameForVolumeMountPoint`
- size: `178`
- prototype: `__int64 __fastcall(wchar_t *, LPWSTR lpszVolumeName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18002cce0`

## callees

- `0x18001236c`
- `0x18009fd20`
- `0x1800a8e8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8f1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8f1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a8eda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a8eda`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800a8f0f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800a8f0f`

## pseudocode

```c
__int64 __fastcall ClusterInternalGetVolumeNameForVolumeMountPoint(wchar_t *a1, LPWSTR lpszVolumeName)
{
  size_t v4; // rsi
  WCHAR *v5; // rbx
  wchar_t *v6; // rax
  unsigned int VolumeNameForVolumeMountPointW; // esi
  size_t v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  if ( StringCchLengthW(a1, (size_t)lpszVolumeName, &v9) )
    return 0;
  v4 = v9;
  if ( a1[v9 - 1] == 92 )
  {
    v5 = a1;
LABEL_8:
    VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(v5, lpszVolumeName, 0x32u);
    goto LABEL_9;
  }
  v6 = (wchar_t *)LocalAlloc(0, 2 * v9 + 4);
  v5 = v6;
  if ( !v6 )
    return 0;
  if ( !(unsigned int)StringCchCopyW(v6, v4 + 2, a1) )
  {
    *(_DWORD *)&v5[v4] = 92;
    goto LABEL_8;
  }
  VolumeNameForVolumeMountPointW = 0;
LABEL_9:
  if ( v5 != a1 )
    LocalFree(v5);
  return VolumeNameForVolumeMountPointW;
}

```

## disassembly

```asm
0x1800a8e8c  mov     rax, rsp
0x1800a8e8f  mov     [rax+8], rbx
0x1800a8e93  mov     [rax+10h], rbp
0x1800a8e97  push    rsi
0x1800a8e98  push    rdi
0x1800a8e99  push    r14
0x1800a8e9b  sub     rsp, 20h
0x1800a8e9f  lea     r8, [rax+20h]; pcchLength
0x1800a8ea3  mov     qword ptr [rax+20h], 0
0x1800a8eab  mov     rbp, rdx
0x1800a8eae  mov     rdi, rcx
0x1800a8eb1  call    StringCchLengthW
0x1800a8eb6  test    eax, eax
0x1800a8eb8  jnz     short loc_1800A8F29
0x1800a8eba  mov     rsi, [rsp+38h+arg_18]
0x1800a8ebf  lea     r14d, [rax+5Ch]
0x1800a8ec3  cmp     [rdi+rsi*2-2], r14w
0x1800a8ec9  jnz     short loc_1800A8ED0
0x1800a8ecb  mov     rbx, rdi
0x1800a8ece  jmp     short loc_1800A8F03
0x1800a8ed0  lea     rdx, ds:4[rsi*2]; uBytes
0x1800a8ed8  xor     ecx, ecx; uFlags
0x1800a8eda  call    cs:__imp_LocalAlloc
0x1800a8ee0  mov     rbx, rax
0x1800a8ee3  test    rax, rax
0x1800a8ee6  jz      short loc_1800A8F29
0x1800a8ee8  lea     rdx, [rsi+2]; unsigned __int64
0x1800a8eec  mov     r8, rdi; wchar_t *
0x1800a8eef  mov     rcx, rax; wchar_t *
0x1800a8ef2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a8ef7  test    eax, eax
0x1800a8ef9  jz      short loc_1800A8EFF
0x1800a8efb  xor     esi, esi
0x1800a8efd  jmp     short loc_1800A8F17
0x1800a8eff  mov     [rbx+rsi*2], r14d
0x1800a8f03  mov     r8d, 32h ; '2'; cchBufferLength
0x1800a8f09  mov     rdx, rbp; lpszVolumeName
0x1800a8f0c  mov     rcx, rbx; lpszVolumeMountPoint
0x1800a8f0f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800a8f15  mov     esi, eax
0x1800a8f17  cmp     rbx, rdi
0x1800a8f1a  jz      short loc_1800A8F25
0x1800a8f1c  mov     rcx, rbx; hMem
0x1800a8f1f  call    cs:__imp_LocalFree
0x1800a8f25  mov     eax, esi
0x1800a8f27  jmp     short loc_1800A8F2B
0x1800a8f29  xor     eax, eax
0x1800a8f2b  mov     rbx, [rsp+38h+arg_0]
0x1800a8f30  mov     rbp, [rsp+38h+arg_8]
0x1800a8f35  add     rsp, 20h
0x1800a8f39  pop     r14
0x1800a8f3b  pop     rdi
0x1800a8f3c  pop     rsi
0x1800a8f3d  retn
```
