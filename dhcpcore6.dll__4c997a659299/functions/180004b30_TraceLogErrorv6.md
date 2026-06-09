# TraceLogErrorv6

- ea: `0x180004b30`
- end: `0x180004c34`
- name: `TraceLogErrorv6`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `47`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ed4`
- `0x180002328`
- `0x1800027e0`
- `0x180003a20`
- `0x180006ed8`
- `0x18000c7dc`
- `0x18000c884`
- `0x18000d340`
- `0x18000d6ac`
- `0x180010340`
- `0x1800108f0`
- `0x180010fd4`
- `0x180011400`
- `0x18001189c`
- `0x180011b98`
- `0x1800128dc`
- `0x180012ee4`
- `0x1800132c0`
- `0x180013410`
- `0x180013580`
- `0x180013700`
- `0x180013840`
- `0x180013a00`
- `0x180014070`
- `0x180014590`
- `0x1800170cc`
- `0x18001c0e4`
- `0x18001cb0c`
- `0x18001e81c`
- `0x18001eac0`
- `0x18001ed84`
- `0x18001ef90`
- `0x18001f630`
- `0x18001f77c`
- `0x18001fc58`
- `0x1800200d8`
- `0x180020824`
- `0x180021150`
- `0x1800216a4`
- `0x18002211c`
- `0x1800225c8`
- `0x180022b80`
- `0x180023344`
- `0x180023c2c`
- `0x180023dc0`
- `0x18002458c`
- `0x180025094`

## callees

- `0x180004b30`
- `0x180004c3c`
- `0x180019ad0`
- `0x18001a3ee`

## pseudocode

```c
__int64 __fastcall TraceLogErrorv6(__int64 a1, int a2, int a3)
{
  __int64 *v6; // rcx
  bool v7; // zf
  __int64 v8; // rdx
  __int64 v9; // r8
  __int16 *v10; // rax
  __int16 *v11; // rcx
  _DWORD v13[26]; // [rsp+20h] [rbp-158h] BYREF
  __int64 v14; // [rsp+88h] [rbp-F0h]
  __int16 v15; // [rsp+C0h] [rbp-B8h] BYREF
  _BYTE v16[158]; // [rsp+C2h] [rbp-B6h] BYREF

  memset_0(v16, 0, sizeof(v16));
  memset_0(v13, 0, 0xA0u);
  v13[0] = a2;
  v15 = 0;
  v13[3] = a3;
  if ( a1 )
  {
    v6 = &qword_180037F50;
    v7 = *(_QWORD *)(a1 + 56) == 0;
    v8 = 80;
    v14 = *(_QWORD *)(a1 + 24);
    v9 = 2147483646;
    if ( !v7 )
      v6 = *(__int64 **)(a1 + 56);
    v13[4] = *(_DWORD *)(a1 + 48);
    v10 = &v15;
    do
    {
      if ( !v9 )
        break;
      if ( !*(_WORD *)v6 )
        break;
      *v10 = *(_WORD *)v6;
      v6 = (__int64 *)((char *)v6 + 2);
      ++v10;
      --v9;
      --v8;
    }
    while ( v8 );
    v11 = v10 - 1;
    if ( v8 )
      v11 = v10;
    *v11 = 0;
  }
  return TraceLogEx(v13);
}

```

## disassembly

```asm
0x180004b30  mov     [rsp+arg_0], rbx
0x180004b35  mov     [rsp+arg_8], rsi
0x180004b3a  push    rdi
0x180004b3b  sub     rsp, 170h
0x180004b42  mov     rax, cs:__security_cookie
0x180004b49  xor     rax, rsp
0x180004b4c  mov     [rsp+178h+var_18], rax
0x180004b54  mov     edi, r8d
0x180004b57  mov     ebx, edx
0x180004b59  mov     rsi, rcx
0x180004b5c  xor     edx, edx; Val
0x180004b5e  mov     r8d, 9Eh; Size
0x180004b64  lea     rcx, [rsp+178h+var_B6]; void *
0x180004b6c  call    memset_0
0x180004b71  xor     edx, edx; Val
0x180004b73  lea     rcx, [rsp+178h+var_158]; void *
0x180004b78  mov     r8d, 0A0h; Size
0x180004b7e  call    memset_0
0x180004b83  xor     r10d, r10d
0x180004b86  mov     [rsp+178h+var_158], ebx
0x180004b8a  mov     [rsp+178h+var_B8], r10w
0x180004b93  mov     [rsp+178h+var_14C], edi
0x180004b97  test    rsi, rsi
0x180004b9a  jz      short loc_180004C04
0x180004b9c  mov     rax, [rsi+18h]
0x180004ba0  lea     rcx, qword_180037F50
0x180004ba7  cmp     [rsi+38h], r10
0x180004bab  lea     edx, [r10+50h]
0x180004baf  mov     [rsp+178h+var_F0], rax
0x180004bb7  mov     r8d, 7FFFFFFEh
0x180004bbd  mov     eax, [rsi+30h]
0x180004bc0  cmovnz  rcx, [rsi+38h]
0x180004bc5  mov     [rsp+178h+var_148], eax
0x180004bc9  lea     rax, [rsp+178h+var_B8]
0x180004bd1  test    r8, r8
0x180004bd4  jz      short loc_180004BF5
0x180004bd6  movzx   r9d, word ptr [rcx]
0x180004bda  test    r9w, r9w
0x180004bde  jz      short loc_180004BF5
0x180004be0  mov     [rax], r9w
0x180004be4  add     rcx, 2
0x180004be8  add     rax, 2
0x180004bec  dec     r8
0x180004bef  sub     rdx, 1
0x180004bf3  jnz     short loc_180004BD1
0x180004bf5  test    rdx, rdx
0x180004bf8  lea     rcx, [rax-2]
0x180004bfc  cmovnz  rcx, rax
0x180004c00  mov     [rcx], r10w
0x180004c04  lea     rcx, [rsp+178h+var_158]
0x180004c09  call    TraceLogEx
0x180004c0e  mov     rcx, [rsp+178h+var_18]
0x180004c16  xor     rcx, rsp; StackCookie
0x180004c19  call    __security_check_cookie
0x180004c1e  lea     r11, [rsp+178h+var_8]
0x180004c26  mov     rbx, [r11+10h]
0x180004c2a  mov     rsi, [r11+18h]
0x180004c2e  mov     rsp, r11
0x180004c31  pop     rdi
0x180004c32  retn
```
