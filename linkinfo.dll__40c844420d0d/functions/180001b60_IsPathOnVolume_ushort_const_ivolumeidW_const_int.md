# IsPathOnVolume(ushort const *,_ivolumeidW const *,int *)

- ea: `0x180001b60`
- end: `0x180001bc4`
- name: `?IsPathOnVolume@@YAHPEBGPEBU_ivolumeidW@@PEAH@Z`
- size: `100`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _ivolumeidW *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800031f0`

## callees

- `0x180001b60`
- `0x1800023f0`
- `0x180003470`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001bb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001bb4`

## pseudocode

```c
int __fastcall IsPathOnVolume(WCHAR *a1, const struct _ivolumeidW *a2, int *a3)
{
  int result; // eax
  int v6; // ebx
  int v7; // eax
  HLOCAL v8; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v10; // [rsp+78h] [rbp+20h] BYREF

  hMem = 0;
  v10 = 0;
  result = CreateVolumeID(a1, (struct _volumeid **)&hMem, &v10);
  v6 = result;
  if ( result )
  {
    v7 = CompareVolumeIDs((__int64)hMem, (__int64)a2);
    v8 = hMem;
    *a3 = v7 == 0;
    LocalFree(v8);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180001b60  push    rbx
0x180001b62  push    rbp
0x180001b63  push    rsi
0x180001b64  push    rdi
0x180001b65  sub     rsp, 38h
0x180001b69  mov     rdi, r8
0x180001b6c  mov     rsi, rdx
0x180001b6f  xor     ebp, ebp
0x180001b71  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x180001b76  lea     rdx, [rsp+58h+hMem]; struct _volumeid **
0x180001b7b  mov     [rsp+58h+hMem], rbp
0x180001b80  mov     [rsp+58h+arg_18], ebp
0x180001b84  call    ?CreateVolumeID@@YAHPEBGPEAPEAU_volumeid@@PEAI@Z; CreateVolumeID(ushort const *,_volumeid * *,uint *)
0x180001b89  mov     ebx, eax
0x180001b8b  test    eax, eax
0x180001b8d  jnz     short loc_180001B99
0x180001b8f  add     rsp, 38h
0x180001b93  pop     rdi
0x180001b94  pop     rsi
0x180001b95  pop     rbp
0x180001b96  pop     rbx
0x180001b97  retn
0x180001b99  mov     rcx, [rsp+58h+hMem]
0x180001b9e  mov     rdx, rsi
0x180001ba1  call    ?CompareVolumeIDs@@YA?AW4_comparisonresult@@PEBU_volumeid@@0@Z; CompareVolumeIDs(_volumeid const *,_volumeid const *)
0x180001ba6  mov     rcx, [rsp+58h+hMem]; hMem
0x180001bab  mov     edx, ebp
0x180001bad  test    eax, eax
0x180001baf  setz    dl
0x180001bb2  mov     [rdi], edx
0x180001bb4  call    cs:__imp_LocalFree
0x180001bbb  nop     dword ptr [rax+rax+00h]
0x180001bc0  mov     eax, ebx
0x180001bc2  jmp     short loc_180001B8F
```
