# FreeExportList

- ea: `0x18000bba4`
- end: `0x18000bc0c`
- name: `FreeExportList`
- size: `104`
- prototype: `__int64 __fastcall(HGLOBAL hMem)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002930`
- `0x180004178`
- `0x18000bc14`

## callees

- `0x18000bba4`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000bbc0`
- `KERNEL32!GlobalFree` at `0x18000bbdb`
- `KERNEL32!GlobalFree` at `0x18000bbe4`
- `KERNEL32!GlobalFree` at `0x18000bbf5`
- `KERNEL32!GlobalFree` at `0x18000bbc0`
- `KERNEL32!GlobalFree` at `0x18000bbdb`
- `KERNEL32!GlobalFree` at `0x18000bbe4`
- `KERNEL32!GlobalFree` at `0x18000bbf5`

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
0x18000bba4  test    rcx, rcx
0x18000bba7  jz      short locret_18000BC0B
0x18000bba9  push    rbx
0x18000bbaa  push    rbp
0x18000bbab  push    rsi
0x18000bbac  push    rdi
0x18000bbad  sub     rsp, 28h
0x18000bbb1  mov     rbx, rcx
0x18000bbb4  mov     rcx, [rbx]; hMem
0x18000bbb7  mov     rsi, [rbx+18h]
0x18000bbbb  test    rcx, rcx
0x18000bbbe  jz      short loc_18000BBC6
0x18000bbc0  call    cs:__imp_GlobalFree
0x18000bbc6  mov     rdi, [rbx+8]
0x18000bbca  test    rdi, rdi
0x18000bbcd  jz      short loc_18000BBF2
0x18000bbcf  mov     rcx, [rdi]; hMem
0x18000bbd2  mov     rbp, [rdi+10h]
0x18000bbd6  test    rcx, rcx
0x18000bbd9  jz      short loc_18000BBE1
0x18000bbdb  call    cs:__imp_GlobalFree
0x18000bbe1  mov     rcx, rdi; hMem
0x18000bbe4  call    cs:__imp_GlobalFree
0x18000bbea  mov     rdi, rbp
0x18000bbed  test    rbp, rbp
0x18000bbf0  jnz     short loc_18000BBCF
0x18000bbf2  mov     rcx, rbx; hMem
0x18000bbf5  call    cs:__imp_GlobalFree
0x18000bbfb  mov     rbx, rsi
0x18000bbfe  test    rsi, rsi
0x18000bc01  jnz     short loc_18000BBB4
0x18000bc03  add     rsp, 28h
0x18000bc07  pop     rdi
0x18000bc08  pop     rsi
0x18000bc09  pop     rbp
0x18000bc0a  pop     rbx
0x18000bc0b  retn
```
