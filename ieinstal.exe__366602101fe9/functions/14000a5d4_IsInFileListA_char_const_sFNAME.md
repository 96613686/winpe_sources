# IsInFileListA(char const *,sFNAME *)

- ea: `0x14000a5d4`
- end: `0x14000a6b1`
- name: `?IsInFileListA@@YAHPEBDPEAUsFNAME@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(const char *, struct sFNAME *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140004a18`
- `0x140007d00`
- `0x140008684`
- `0x140009cc4`

## callees

- `0x140001af3`
- `0x14000a5d4`
- `0x14000b700`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x14000a669`
- `KERNEL32!lstrcmpiA` at `0x14000a669`

## pseudocode

```c
__int64 __fastcall IsInFileListA(const BYTE *a1, LPCSTR *a2)
{
  unsigned int v4; // esi
  CHAR v5; // al
  CHAR *p_String1; // rcx
  CHAR String1; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v9[271]; // [rsp+31h] [rbp-127h] BYREF

  v4 = 0;
  String1 = 0;
  memset_0(v9, 0, 0x103u);
  if ( (int)StringCchCopyExA(&String1, 0x104u, a1, 0, 0, 0x100u) >= 0 )
  {
    v5 = String1;
    if ( String1 )
    {
      p_String1 = &String1;
      do
      {
        if ( v5 == 47 )
          *p_String1 = 92;
        v5 = *++p_String1;
      }
      while ( *p_String1 );
    }
    while ( a2 )
    {
      if ( *a2 && !lstrcmpiA(&String1, *a2) )
        return 1;
      a2 = (LPCSTR *)a2[1];
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000a5d4  mov     [rsp+arg_10], rbx
0x14000a5d9  mov     [rsp+arg_18], rsi
0x14000a5de  push    rdi
0x14000a5df  sub     rsp, 150h
0x14000a5e6  mov     rax, cs:__security_cookie
0x14000a5ed  xor     rax, rsp
0x14000a5f0  mov     [rsp+158h+var_18], rax
0x14000a5f8  mov     rdi, rdx
0x14000a5fb  mov     rbx, rcx
0x14000a5fe  xor     esi, esi
0x14000a600  lea     rcx, [rsp+158h+var_127]; void *
0x14000a605  xor     edx, edx; Val
0x14000a607  mov     [rsp+158h+String1], sil
0x14000a60c  mov     r8d, 103h; Size
0x14000a612  call    memset_0
0x14000a617  xor     r9d, r9d; char **
0x14000a61a  mov     [rsp+158h+var_130], 100h; unsigned int
0x14000a622  mov     r8, rbx; char *
0x14000a625  mov     [rsp+158h+var_138], rsi; unsigned __int64 *
0x14000a62a  mov     edx, 104h; Size
0x14000a62f  lea     rcx, [rsp+158h+String1]; char *
0x14000a634  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x14000a639  test    eax, eax
0x14000a63b  js      short loc_14000A689
0x14000a63d  mov     al, [rsp+158h+String1]
0x14000a641  test    al, al
0x14000a643  jz      short loc_14000A67D
0x14000a645  lea     rcx, [rsp+158h+String1]
0x14000a64a  cmp     al, 2Fh ; '/'
0x14000a64c  jnz     short loc_14000A651
0x14000a64e  mov     byte ptr [rcx], 5Ch ; '\'
0x14000a651  inc     rcx
0x14000a654  mov     al, [rcx]
0x14000a656  test    al, al
0x14000a658  jnz     short loc_14000A64A
0x14000a65a  jmp     short loc_14000A67D
0x14000a65c  mov     rdx, [rdi]; lpString2
0x14000a65f  test    rdx, rdx
0x14000a662  jz      short loc_14000A679
0x14000a664  lea     rcx, [rsp+158h+String1]; lpString1
0x14000a669  call    cs:__imp_lstrcmpiA
0x14000a670  nop     dword ptr [rax+rax+00h]
0x14000a675  test    eax, eax
0x14000a677  jz      short loc_14000A684
0x14000a679  mov     rdi, [rdi+8]
0x14000a67d  test    rdi, rdi
0x14000a680  jnz     short loc_14000A65C
0x14000a682  jmp     short loc_14000A689
0x14000a684  mov     esi, 1
0x14000a689  mov     eax, esi
0x14000a68b  mov     rcx, [rsp+158h+var_18]
0x14000a693  xor     rcx, rsp; StackCookie
0x14000a696  call    __security_check_cookie
0x14000a69b  lea     r11, [rsp+158h+var_8]
0x14000a6a3  mov     rbx, [r11+20h]
0x14000a6a7  mov     rsi, [r11+28h]
0x14000a6ab  mov     rsp, r11
0x14000a6ae  pop     rdi
0x14000a6af  retn
```
