# CleanupCFile

- ea: `0x180002f38`
- end: `0x180002fac`
- name: `CleanupCFile`
- size: `116`
- prototype: `HLOCAL __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fb4`
- `0x180005910`

## callees

- `0x180002e7c`
- `0x180002f38`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180002f78`
- `KERNEL32!LocalFree` at `0x180002f8f`
- `KERNEL32!LocalFree` at `0x180002f78`
- `KERNEL32!LocalFree` at `0x180002f8f`
- `KERNEL32!LocalFree` at `0x180002fa5`

## pseudocode

```c
HLOCAL __fastcall CleanupCFile(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
  v2 = (void *)a1[2];
  if ( v2 )
  {
    LocalFree(v2);
    a1[2] = 0;
  }
  v3 = (void *)a1[3];
  if ( v3 )
  {
    LocalFree(v3);
    a1[3] = 0;
  }
  return LocalFree(a1);
}

```

## disassembly

```asm
0x180002f38  push    rbx
0x180002f3a  sub     rsp, 20h
0x180002f3e  mov     rbx, rcx
0x180002f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f48  lea     rax, WPP_GLOBAL_Control
0x180002f4f  cmp     rcx, rax
0x180002f52  jz      short loc_180002F6F
0x180002f54  test    byte ptr [rcx+1Ch], 1
0x180002f58  jz      short loc_180002F6F
0x180002f5a  mov     rcx, [rcx+10h]
0x180002f5e  lea     r8, WPP_bc5dfa190b42335729027cd8699dae89_Traceguids
0x180002f65  mov     edx, 2Dh ; '-'
0x180002f6a  call    WPP_SF_
0x180002f6f  mov     rcx, [rbx+10h]; hMem
0x180002f73  test    rcx, rcx
0x180002f76  jz      short loc_180002F86
0x180002f78  call    cs:__imp_LocalFree
0x180002f7e  mov     qword ptr [rbx+10h], 0
0x180002f86  mov     rcx, [rbx+18h]; hMem
0x180002f8a  test    rcx, rcx
0x180002f8d  jz      short loc_180002F9D
0x180002f8f  call    cs:__imp_LocalFree
0x180002f95  mov     qword ptr [rbx+18h], 0
0x180002f9d  mov     rcx, rbx
0x180002fa0  add     rsp, 20h
0x180002fa4  pop     rbx
0x180002fa5  jmp     cs:__imp_LocalFree
```
