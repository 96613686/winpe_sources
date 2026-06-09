# DeleteExtractedFiles(char *,sFNAME *)

- ea: `0x140009824`
- end: `0x1400098f7`
- name: `?DeleteExtractedFiles@@YAJPEADPEAUsFNAME@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(char *, struct sFNAME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140005924`

## callees

- `0x140001af3`
- `0x140008a0c`
- `0x140009824`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x14000989c`
- `KERNEL32!SetFileAttributesA` at `0x14000989c`
- `KERNEL32!DeleteFileA` at `0x1400098b1`
- `KERNEL32!DeleteFileA` at `0x1400098b1`

## pseudocode

```c
__int64 __fastcall DeleteExtractedFiles(char *a1, struct sFNAME *a2)
{
  unsigned int v2; // edi
  struct sFNAME *i; // rbx
  CHAR FileName; // [rsp+20h] [rbp-128h] BYREF
  _BYTE v7[271]; // [rsp+21h] [rbp-127h] BYREF

  v2 = 0;
  for ( i = a2; i; i = (struct sFNAME *)*((_QWORD *)i + 1) )
  {
    if ( !*((_DWORD *)i + 4) )
    {
      if ( *(_QWORD *)i )
      {
        FileName = 0;
        memset_0(v7, 0, 0x103u);
        if ( !(unsigned int)CatDirAndFileA(a1, *(const char **)i, 0x104u, &FileName)
          || !SetFileAttributesA(&FileName, 0x80u)
          || !DeleteFileA(&FileName) )
        {
          v2 = 1;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140009824  mov     [rsp+arg_10], rbx
0x140009829  mov     [rsp+arg_18], rsi
0x14000982e  push    rdi
0x14000982f  sub     rsp, 140h
0x140009836  mov     rax, cs:__security_cookie
0x14000983d  xor     rax, rsp
0x140009840  mov     [rsp+148h+var_18], rax
0x140009848  xor     edi, edi
0x14000984a  mov     rbx, rdx
0x14000984d  mov     rsi, rcx
0x140009850  test    rdx, rdx
0x140009853  jz      short loc_1400098CF
0x140009855  cmp     dword ptr [rbx+10h], 0
0x140009859  jnz     short loc_1400098C6
0x14000985b  cmp     qword ptr [rbx], 0
0x14000985f  jz      short loc_1400098C6
0x140009861  xor     edx, edx; Val
0x140009863  mov     [rsp+148h+FileName], 0
0x140009868  mov     r8d, 103h; Size
0x14000986e  lea     rcx, [rsp+148h+var_127]; void *
0x140009873  call    memset_0
0x140009878  mov     rdx, [rbx]; char *
0x14000987b  lea     r9, [rsp+148h+FileName]; char *
0x140009880  mov     r8d, 104h; unsigned int
0x140009886  mov     rcx, rsi; char *
0x140009889  call    ?CatDirAndFileA@@YAHPEBD0KPEAD@Z; CatDirAndFileA(char const *,char const *,ulong,char *)
0x14000988e  test    eax, eax
0x140009890  jz      short loc_1400098C1
0x140009892  mov     edx, 80h; dwFileAttributes
0x140009897  lea     rcx, [rsp+148h+FileName]; lpFileName
0x14000989c  call    cs:__imp_SetFileAttributesA
0x1400098a3  nop     dword ptr [rax+rax+00h]
0x1400098a8  test    eax, eax
0x1400098aa  jz      short loc_1400098C1
0x1400098ac  lea     rcx, [rsp+148h+FileName]; lpFileName
0x1400098b1  call    cs:__imp_DeleteFileA
0x1400098b8  nop     dword ptr [rax+rax+00h]
0x1400098bd  test    eax, eax
0x1400098bf  jnz     short loc_1400098C6
0x1400098c1  mov     edi, 1
0x1400098c6  mov     rbx, [rbx+8]
0x1400098ca  test    rbx, rbx
0x1400098cd  jnz     short loc_140009855
0x1400098cf  mov     eax, edi
0x1400098d1  mov     rcx, [rsp+148h+var_18]
0x1400098d9  xor     rcx, rsp; StackCookie
0x1400098dc  call    __security_check_cookie
0x1400098e1  lea     r11, [rsp+148h+var_8]
0x1400098e9  mov     rbx, [r11+20h]
0x1400098ed  mov     rsi, [r11+28h]
0x1400098f1  mov     rsp, r11
0x1400098f4  pop     rdi
0x1400098f5  retn
```
