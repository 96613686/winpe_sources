# AslFileGetVersionForPath

- ea: `0x18000d824`
- end: `0x18000d907`
- name: `AslFileGetVersionForPath`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800039c8`

## callees

- `0x18000d258`
- `0x18000d824`
- `0x18000d910`
- `0x18000dc10`
- `0x1800191a2`
- `0x1800191f0`

## pseudocode

```c
__int64 __fastcall AslFileGetVersionForPath(_DWORD *a1, _DWORD *a2, _DWORD *a3, const WCHAR *a4)
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
    Attributes = AslFileAllocAndGetAttributes(v12, P[0], 8);
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
0x18000d824  push    rbx
0x18000d826  push    rsi
0x18000d827  push    rdi
0x18000d828  push    r14
0x18000d82a  sub     rsp, 4D8h
0x18000d831  mov     rax, cs:__security_cookie
0x18000d838  xor     rax, rsp
0x18000d83b  mov     [rsp+4F8h+var_38], rax
0x18000d843  mov     r14, r8
0x18000d846  mov     [rsp+4F8h+P], 0
0x18000d84f  mov     rsi, rdx
0x18000d852  mov     rdi, rcx
0x18000d855  xor     edx, edx; Val
0x18000d857  lea     rcx, [rsp+4F8h+var_4B8]; void *
0x18000d85c  mov     r8d, 480h; Size
0x18000d862  mov     rbx, r9
0x18000d865  call    memset_0
0x18000d86a  mov     dword ptr [rdi], 0
0x18000d870  lea     rcx, [rsp+4F8h+P]
0x18000d875  mov     dword ptr [rsi], 0
0x18000d87b  mov     rdx, rbx
0x18000d87e  mov     dword ptr [r14], 0
0x18000d885  call    AslFileMappingCreate
0x18000d88a  mov     ebx, eax
0x18000d88c  test    eax, eax
0x18000d88e  js      short loc_18000D8DE
0x18000d890  mov     rdx, [rsp+4F8h+P]
0x18000d895  lea     rcx, [rsp+4F8h+var_4B8]
0x18000d89a  mov     r8d, 8
0x18000d8a0  call    AslFileAllocAndGetAttributes
0x18000d8a5  mov     ebx, eax
0x18000d8a7  test    eax, eax
0x18000d8a9  js      short loc_18000D8DE
0x18000d8ab  test    [rsp+4F8h+var_440], 1
0x18000d8b3  jz      short loc_18000D8DC
0x18000d8b5  mov     rdx, [rsp+4F8h+var_448]
0x18000d8bd  mov     rax, rdx
0x18000d8c0  shr     rax, 30h
0x18000d8c4  mov     [rdi], eax
0x18000d8c6  mov     rax, rdx
0x18000d8c9  shr     rax, 20h
0x18000d8cd  movzx   eax, ax
0x18000d8d0  mov     [rsi], eax
0x18000d8d2  shr     rdx, 10h
0x18000d8d6  movzx   eax, dx
0x18000d8d9  mov     [r14], eax
0x18000d8dc  xor     ebx, ebx
0x18000d8de  mov     rcx, [rsp+4F8h+P]; P
0x18000d8e3  call    AslFileMappingDelete
0x18000d8e8  mov     eax, ebx
0x18000d8ea  mov     rcx, [rsp+4F8h+var_38]
0x18000d8f2  xor     rcx, rsp; StackCookie
0x18000d8f5  call    __security_check_cookie
0x18000d8fa  add     rsp, 4D8h
0x18000d901  pop     r14
0x18000d903  pop     rdi
0x18000d904  pop     rsi
0x18000d905  pop     rbx
0x18000d906  retn
```
