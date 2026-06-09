# FreeExportList

- ea: `0x18000c450`
- end: `0x18000c4d1`
- name: `FreeExportList`
- size: `129`
- prototype: `HGLOBAL __fastcall(HGLOBAL *hMem)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a90`
- `0x180004348`
- `0x18000c4d8`

## callees

- `0x18000c450`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000c46c`
- `KERNEL32!GlobalFree` at `0x18000c48d`
- `KERNEL32!GlobalFree` at `0x18000c49c`
- `KERNEL32!GlobalFree` at `0x18000c4b3`
- `KERNEL32!GlobalFree` at `0x18000c46c`
- `KERNEL32!GlobalFree` at `0x18000c48d`
- `KERNEL32!GlobalFree` at `0x18000c49c`
- `KERNEL32!GlobalFree` at `0x18000c4b3`

## pseudocode

```c
HGLOBAL __fastcall FreeExportList(HGLOBAL *hMem)
{
  HGLOBAL *v1; // rbx
  HGLOBAL *v2; // rsi
  HGLOBAL *v3; // rdi
  HGLOBAL *v4; // rbp
  HGLOBAL result; // rax

  if ( hMem )
  {
    v1 = hMem;
    do
    {
      v2 = (HGLOBAL *)v1[3];
      if ( *v1 )
        GlobalFree(*v1);
      v3 = (HGLOBAL *)v1[1];
      if ( v3 )
      {
        do
        {
          v4 = (HGLOBAL *)v3[2];
          if ( *v3 )
            GlobalFree(*v3);
          GlobalFree(v3);
          v3 = v4;
        }
        while ( v4 );
      }
      result = GlobalFree(v1);
      v1 = v2;
    }
    while ( v2 );
  }
  return result;
}

```

## disassembly

```asm
0x18000c450  test    rcx, rcx
0x18000c453  jz      short locret_18000C4CF
0x18000c455  push    rbx
0x18000c456  push    rbp
0x18000c457  push    rsi
0x18000c458  push    rdi
0x18000c459  sub     rsp, 28h
0x18000c45d  mov     rbx, rcx
0x18000c460  mov     rcx, [rbx]; hMem
0x18000c463  mov     rsi, [rbx+18h]
0x18000c467  test    rcx, rcx
0x18000c46a  jz      short loc_18000C478
0x18000c46c  call    cs:__imp_GlobalFree
0x18000c473  nop     dword ptr [rax+rax+00h]
0x18000c478  mov     rdi, [rbx+8]
0x18000c47c  test    rdi, rdi
0x18000c47f  jz      short loc_18000C4B0
0x18000c481  mov     rcx, [rdi]; hMem
0x18000c484  mov     rbp, [rdi+10h]
0x18000c488  test    rcx, rcx
0x18000c48b  jz      short loc_18000C499
0x18000c48d  call    cs:__imp_GlobalFree
0x18000c494  nop     dword ptr [rax+rax+00h]
0x18000c499  mov     rcx, rdi; hMem
0x18000c49c  call    cs:__imp_GlobalFree
0x18000c4a3  nop     dword ptr [rax+rax+00h]
0x18000c4a8  mov     rdi, rbp
0x18000c4ab  test    rbp, rbp
0x18000c4ae  jnz     short loc_18000C481
0x18000c4b0  mov     rcx, rbx; hMem
0x18000c4b3  call    cs:__imp_GlobalFree
0x18000c4ba  nop     dword ptr [rax+rax+00h]
0x18000c4bf  mov     rbx, rsi
0x18000c4c2  test    rsi, rsi
0x18000c4c5  jnz     short loc_18000C460
0x18000c4c7  add     rsp, 28h
0x18000c4cb  pop     rdi
0x18000c4cc  pop     rsi
0x18000c4cd  pop     rbp
0x18000c4ce  pop     rbx
0x18000c4cf  retn
```
