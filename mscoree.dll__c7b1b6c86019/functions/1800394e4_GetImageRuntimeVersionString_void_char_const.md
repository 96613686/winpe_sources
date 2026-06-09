# GetImageRuntimeVersionString(void *,char const * *)

- ea: `0x1800394e4`
- end: `0x1800395de`
- name: `?GetImageRuntimeVersionString@@YAJPEAXPEAPEBD@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *, const char **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b5e8`

## callees

- `0x1800394e4`
- `0x180042280`

## string_xrefs

- `0x1800395b2`: `COMPLUS`

## pseudocode

```c
__int64 __fastcall GetImageRuntimeVersionString(char *a1, const char **a2)
{
  char *v5; // rbx
  unsigned __int64 v6; // rax
  bool v7; // zf
  int v8; // eax
  unsigned __int8 *v9; // rax
  int v10; // r8d
  int v11; // edx
  char *v12; // rdx
  int v13; // ecx

  if ( *(_DWORD *)a1 != 1112167234 )
    return 2148733198LL;
  if ( *((_WORD *)a1 + 2) && (*((_WORD *)a1 + 2) != 1 || *((_WORD *)a1 + 3)) )
  {
    v5 = a1 + 16;
    *a2 = a1 + 16;
    if ( a1 == (char *)-16LL )
      return 0;
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 >= 5 && !strncmp(a1 + 16, "v1.", 3u) )
    {
      if ( a1[20] == 46 )
      {
        v7 = v5[3] == 48;
        goto LABEL_15;
      }
      v8 = strncmp(a1 + 19, "x86", 3u);
    }
    else
    {
      v9 = (unsigned __int8 *)v5;
      do
      {
        v10 = v9["retail" - v5];
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( !v11 )
        goto LABEL_16;
      v12 = (char *)("COMPLUS" - v5);
      do
      {
        v13 = (unsigned __int8)v12[(_QWORD)v5];
        v8 = (unsigned __int8)*v5 - v13;
        if ( v8 )
          break;
        ++v5;
      }
      while ( v13 );
    }
    v7 = v8 == 0;
LABEL_15:
    if ( v7 )
LABEL_16:
      *a2 = "v1.0.3705";
    return 0;
  }
  return 2148733191LL;
}

```

## disassembly

```asm
0x1800394e4  push    rbx
0x1800394e6  push    rbp
0x1800394e7  push    rsi
0x1800394e8  push    rdi
0x1800394e9  sub     rsp, 28h
0x1800394ed  cmp     dword ptr [rcx], 424A5342h
0x1800394f3  mov     rsi, rdx
0x1800394f6  mov     rdi, rcx
0x1800394f9  jz      short loc_180039505
0x1800394fb  mov     eax, 8013110Eh
0x180039500  jmp     loc_1800395D5
0x180039505  mov     ebp, 1
0x18003950a  cmp     [rcx+4], bp
0x18003950e  jb      loc_1800395D0
0x180039514  jnz     short loc_180039520
0x180039516  cmp     [rcx+6], bp
0x18003951a  jb      loc_1800395D0
0x180039520  lea     rbx, [rcx+10h]
0x180039524  mov     [rdx], rbx
0x180039527  test    rbx, rbx
0x18003952a  jz      short loc_180039588
0x18003952c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039530  inc     rax
0x180039533  cmp     byte ptr [rbx+rax], 0
0x180039537  jnz     short loc_180039530
0x180039539  cmp     rax, 5
0x18003953d  jb      short loc_18003958C
0x18003953f  mov     r8d, 3; MaxCount
0x180039545  lea     rdx, Str2; "v1."
0x18003954c  mov     rcx, rbx; Str1
0x18003954f  call    strncmp
0x180039554  test    eax, eax
0x180039556  jnz     short loc_18003958C
0x180039558  cmp     byte ptr [rdi+14h], 2Eh ; '.'
0x18003955c  jnz     short loc_180039564
0x18003955e  cmp     byte ptr [rbx+3], 30h ; '0'
0x180039562  jmp     short loc_18003957C
0x180039564  lea     rcx, [rdi+13h]; Str1
0x180039568  mov     r8d, 3; MaxCount
0x18003956e  lea     rdx, aX86; "x86"
0x180039575  call    strncmp
0x18003957a  test    eax, eax
0x18003957c  jnz     short loc_180039588
0x18003957e  lea     rax, aV103705_0; "v1.0.3705"
0x180039585  mov     [rsi], rax
0x180039588  xor     eax, eax
0x18003958a  jmp     short loc_1800395D5
0x18003958c  lea     rcx, aRetail; "retail"
0x180039593  mov     rax, rbx
0x180039596  sub     rcx, rbx
0x180039599  movzx   edx, byte ptr [rax]
0x18003959c  movzx   r8d, byte ptr [rax+rcx]
0x1800395a1  sub     edx, r8d
0x1800395a4  jnz     short loc_1800395AE
0x1800395a6  add     rax, rbp
0x1800395a9  test    r8d, r8d
0x1800395ac  jnz     short loc_180039599
0x1800395ae  test    edx, edx
0x1800395b0  jz      short loc_18003957E
0x1800395b2  lea     rdx, aComplus_0; "COMPLUS"
0x1800395b9  sub     rdx, rbx
0x1800395bc  movzx   eax, byte ptr [rbx]
0x1800395bf  movzx   ecx, byte ptr [rbx+rdx]
0x1800395c3  sub     eax, ecx
0x1800395c5  jnz     short loc_18003957A
0x1800395c7  add     rbx, rbp
0x1800395ca  test    ecx, ecx
0x1800395cc  jnz     short loc_1800395BC
0x1800395ce  jmp     short loc_18003957A
0x1800395d0  mov     eax, 80131107h
0x1800395d5  add     rsp, 28h
0x1800395d9  pop     rdi
0x1800395da  pop     rsi
0x1800395db  pop     rbp
0x1800395dc  pop     rbx
0x1800395dd  retn
```
