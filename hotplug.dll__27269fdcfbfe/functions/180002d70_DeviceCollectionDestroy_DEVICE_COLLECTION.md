# DeviceCollectionDestroy(DEVICE_COLLECTION *)

- ea: `0x180002d70`
- end: `0x180002de0`
- name: `?DeviceCollectionDestroy@@YAXPEAUDEVICE_COLLECTION@@@Z`
- size: `112`
- prototype: `void __fastcall(struct DEVICE_COLLECTION *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002824`
- `0x180004aec`
- `0x180004c20`
- `0x180004e60`
- `0x180005140`
- `0x180005430`
- `0x180006eac`
- `0x18000712c`

## callees

- `0x180002d70`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180002da7`
- `KERNEL32!LocalFree` at `0x180002db0`
- `KERNEL32!LocalFree` at `0x180002da7`
- `KERNEL32!LocalFree` at `0x180002db0`
- `COMCTL32!ImageList_Destroy` at `0x180002dc8`
- `COMCTL32!ImageList_Destroy` at `0x180002dc8`

## pseudocode

```c
void __fastcall DeviceCollectionDestroy(struct DEVICE_COLLECTION *a1)
{
  struct DEVICE_COLLECTION *v2; // rdi
  __int64 v3; // rax
  void *v4; // rcx
  struct _IMAGELIST *v5; // rcx

  while ( 1 )
  {
    v2 = *(struct DEVICE_COLLECTION **)a1;
    if ( *(struct DEVICE_COLLECTION **)a1 == a1 )
      break;
    if ( *((struct DEVICE_COLLECTION **)v2 + 1) != a1
      || (v3 = *(_QWORD *)v2, *(struct DEVICE_COLLECTION **)(*(_QWORD *)v2 + 8LL) != v2) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)a1 = v3;
    *(_QWORD *)(v3 + 8) = a1;
    v4 = (void *)*((_QWORD *)v2 + 53);
    if ( v4 )
      LocalFree(v4);
    LocalFree(v2);
  }
  v5 = (struct _IMAGELIST *)*((_QWORD *)a1 + 3);
  if ( v5 )
    ImageList_Destroy(v5);
  *((_DWORD *)a1 + 4) = 0;
}

```

## disassembly

```asm
0x180002d70  mov     [rsp+arg_0], rbx
0x180002d75  push    rdi
0x180002d76  sub     rsp, 20h
0x180002d7a  mov     rbx, rcx
0x180002d7d  mov     rdi, [rbx]
0x180002d80  cmp     rdi, rbx
0x180002d83  jz      short loc_180002DBF
0x180002d85  cmp     [rdi+8], rbx
0x180002d89  jnz     short loc_180002DB8
0x180002d8b  mov     rax, [rdi]
0x180002d8e  cmp     [rax+8], rdi
0x180002d92  jnz     short loc_180002DB8
0x180002d94  mov     [rbx], rax
0x180002d97  mov     [rax+8], rbx
0x180002d9b  mov     rcx, [rdi+1A8h]; hMem
0x180002da2  test    rcx, rcx
0x180002da5  jz      short loc_180002DAD
0x180002da7  call    cs:__imp_LocalFree
0x180002dad  mov     rcx, rdi; hMem
0x180002db0  call    cs:__imp_LocalFree
0x180002db6  jmp     short loc_180002D7D
0x180002db8  mov     ecx, 3
0x180002dbd  int     29h; Win8: RtlFailFast(ecx)
0x180002dbf  mov     rcx, [rbx+18h]; himl
0x180002dc3  test    rcx, rcx
0x180002dc6  jz      short loc_180002DCE
0x180002dc8  call    cs:__imp_ImageList_Destroy
0x180002dce  mov     dword ptr [rbx+10h], 0
0x180002dd5  mov     rbx, [rsp+28h+arg_0]
0x180002dda  add     rsp, 20h
0x180002dde  pop     rdi
0x180002ddf  retn
```
