# AslFileGetVersionForPath

- ea: `0x140007184`
- end: `0x140007261`
- name: `AslFileGetVersionForPath`
- size: `221`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140003cd8`

## callees

- `0x14000233f`
- `0x140007184`
- `0x14000ba04`
- `0x14000bd04`
- `0x14000c630`
- `0x1400115f0`

## pseudocode

```c
__int64 __fastcall AslFileGetVersionForPath(_DWORD *a1, _DWORD *a2, _DWORD *a3, __int64 a4)
{
  int Attributes; // ebx
  unsigned __int64 v9; // rdx
  PVOID P[2]; // [rsp+30h] [rbp-4C8h] BYREF
  _BYTE v12[112]; // [rsp+40h] [rbp-4B8h] BYREF
  unsigned __int64 v13; // [rsp+B0h] [rbp-448h]
  char v14; // [rsp+B8h] [rbp-440h]

  P[0] = 0;
  memset_0(v12, 0, 0x480u);
  *a1 = 0;
  *a2 = 0;
  *a3 = 0;
  Attributes = AslFileMappingCreate(P, a4);
  if ( Attributes >= 0 )
  {
    Attributes = AslFileAllocAndGetAttributes(v12, P[0]);
    if ( Attributes >= 0 )
    {
      if ( (v14 & 1) != 0 )
      {
        v9 = v13;
        *a1 = HIWORD(v13);
        *a2 = WORD2(v9);
        *a3 = WORD1(v9);
      }
      Attributes = 0;
    }
  }
  AslFileMappingDelete(P[0]);
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x140007184  push    rbx
0x140007186  push    rsi
0x140007187  push    rdi
0x140007188  push    r14
0x14000718a  sub     rsp, 4D8h
0x140007191  mov     rax, cs:__security_cookie
0x140007198  xor     rax, rsp
0x14000719b  mov     [rsp+4F8h+var_38], rax
0x1400071a3  mov     r14, r8
0x1400071a6  mov     [rsp+4F8h+P], 0
0x1400071af  mov     rsi, rdx
0x1400071b2  mov     rdi, rcx
0x1400071b5  xor     edx, edx; Val
0x1400071b7  lea     rcx, [rsp+4F8h+var_4B8]; void *
0x1400071bc  mov     r8d, 480h; Size
0x1400071c2  mov     rbx, r9
0x1400071c5  call    memset_0
0x1400071ca  mov     dword ptr [rdi], 0
0x1400071d0  lea     rcx, [rsp+4F8h+P]
0x1400071d5  mov     dword ptr [rsi], 0
0x1400071db  mov     rdx, rbx
0x1400071de  mov     dword ptr [r14], 0
0x1400071e5  call    AslFileMappingCreate
0x1400071ea  mov     ebx, eax
0x1400071ec  test    eax, eax
0x1400071ee  js      short loc_140007238
0x1400071f0  mov     rdx, [rsp+4F8h+P]
0x1400071f5  lea     rcx, [rsp+4F8h+var_4B8]
0x1400071fa  call    AslFileAllocAndGetAttributes
0x1400071ff  mov     ebx, eax
0x140007201  test    eax, eax
0x140007203  js      short loc_140007238
0x140007205  test    [rsp+4F8h+var_440], 1
0x14000720d  jz      short loc_140007236
0x14000720f  mov     rdx, [rsp+4F8h+var_448]
0x140007217  mov     rax, rdx
0x14000721a  shr     rax, 30h
0x14000721e  mov     [rdi], eax
0x140007220  mov     rax, rdx
0x140007223  shr     rax, 20h
0x140007227  movzx   eax, ax
0x14000722a  mov     [rsi], eax
0x14000722c  shr     rdx, 10h
0x140007230  movzx   eax, dx
0x140007233  mov     [r14], eax
0x140007236  xor     ebx, ebx
0x140007238  mov     rcx, [rsp+4F8h+P]; P
0x14000723d  call    AslFileMappingDelete
0x140007242  mov     eax, ebx
0x140007244  mov     rcx, [rsp+4F8h+var_38]
0x14000724c  xor     rcx, rsp; StackCookie
0x14000724f  call    __security_check_cookie
0x140007254  add     rsp, 4D8h
0x14000725b  pop     r14
0x14000725d  pop     rdi
0x14000725e  pop     rsi
0x14000725f  pop     rbx
0x140007260  retn
```
