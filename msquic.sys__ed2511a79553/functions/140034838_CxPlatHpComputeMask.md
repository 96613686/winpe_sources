# CxPlatHpComputeMask

- ea: `0x140034838`
- end: `0x140034955`
- name: `CxPlatHpComputeMask`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012c80`
- `0x140017580`

## callees

- `0x140034838`
- `0x14003c8e0`

## import_xrefs

- `cng!BCryptEncrypt` at `0x1400348de`
- `cng!BCryptEncrypt` at `0x14003492a`
- `cng!BCryptEncrypt` at `0x1400348de`
- `cng!BCryptEncrypt` at `0x14003492a`

## pseudocode

```c
int __fastcall CxPlatHpComputeMask(__int64 a1, unsigned __int8 a2, UCHAR *a3, UCHAR *pbOutput)
{
  unsigned int v4; // ebx
  bool v5; // zf
  int result; // eax
  unsigned int v10; // esi
  int v11; // ebp
  ULONG pcbResult; // [rsp+50h] [rbp-68h] BYREF
  UCHAR pbInput[4]; // [rsp+54h] [rbp-64h] BYREF
  char v14; // [rsp+58h] [rbp-60h]

  v4 = a2;
  v5 = *(_DWORD *)(a1 + 8) == 2;
  pcbResult = 0;
  result = 0;
  if ( !v5 )
    return BCryptEncrypt(*(BCRYPT_KEY_HANDLE *)a1, a3, 16 * a2, 0, 0, 0, pbOutput, 16 * a2, &pcbResult, 0);
  *(_DWORD *)pbInput = 0;
  v10 = 0;
  v14 = 0;
  v11 = 0;
  *(_DWORD *)(a1 + 32) = 16;
  if ( a2 )
  {
    do
    {
      *(_QWORD *)(a1 + 24) = &a3[v11];
      result = BCryptEncrypt(
                 *(BCRYPT_KEY_HANDLE *)a1,
                 pbInput,
                 5u,
                 (void *)(a1 + 16),
                 0,
                 0,
                 &pbOutput[v11],
                 0x10u,
                 &pcbResult,
                 0);
      if ( result < 0 )
        break;
      ++v10;
      v11 += 16;
    }
    while ( v10 < v4 );
  }
  return result;
}

```

## disassembly

```asm
0x140034838  push    rbx
0x14003483a  push    rbp
0x14003483b  push    rsi
0x14003483c  push    rdi
0x14003483d  push    r12
0x14003483f  push    r13
0x140034841  push    r14
0x140034843  push    r15
0x140034845  sub     rsp, 78h
0x140034849  mov     rax, cs:__security_cookie
0x140034850  xor     rax, rsp
0x140034853  mov     [rsp+0B8h+var_58], rax
0x140034858  xor     r13d, r13d
0x14003485b  movzx   ebx, dl
0x14003485e  cmp     dword ptr [rcx+8], 2
0x140034862  mov     r15, r9
0x140034865  mov     r14, r8
0x140034868  mov     [rsp+0B8h+var_68], r13d
0x14003486d  mov     rdi, rcx
0x140034870  mov     eax, r13d
0x140034873  jnz     loc_1400348F9
0x140034879  mov     dword ptr [rsp+0B8h+pbInput], r13d
0x14003487e  mov     esi, r13d
0x140034881  mov     [rsp+0B8h+var_60], r13b
0x140034886  mov     ebp, r13d
0x140034889  mov     dword ptr [rcx+20h], 10h
0x140034890  test    dl, dl
0x140034892  jz      loc_140034936
0x140034898  mov     [rsp+0B8h+dwFlags], r13d; dwFlags
0x14003489d  lea     r9, [rdi+10h]; pPaddingInfo
0x1400348a1  mov     ecx, ebp
0x1400348a3  lea     rdx, [rsp+0B8h+pbInput]; pbInput
0x1400348a8  mov     r8d, 5; cbInput
0x1400348ae  lea     rax, [rcx+r14]
0x1400348b2  mov     [rdi+18h], rax
0x1400348b6  lea     rax, [rcx+r15]
0x1400348ba  lea     rcx, [rsp+0B8h+var_68]
0x1400348bf  mov     [rsp+0B8h+pcbResult], rcx; pcbResult
0x1400348c4  mov     rcx, [rdi]; hKey
0x1400348c7  mov     [rsp+0B8h+cbOutput], 10h; cbOutput
0x1400348cf  mov     [rsp+0B8h+pbOutput], rax; pbOutput
0x1400348d4  mov     [rsp+0B8h+cbIV], r13d; cbIV
0x1400348d9  mov     [rsp+0B8h+pbIV], r13; pbIV
0x1400348de  call    cs:__imp_BCryptEncrypt
0x1400348e5  nop     dword ptr [rax+rax+00h]
0x1400348ea  test    eax, eax
0x1400348ec  js      short loc_140034936
0x1400348ee  inc     esi
0x1400348f0  add     ebp, 10h
0x1400348f3  cmp     esi, ebx
0x1400348f5  jb      short loc_140034898
0x1400348f7  jmp     short loc_140034936
0x1400348f9  mov     rcx, [rcx]; hKey
0x1400348fc  lea     rax, [rsp+0B8h+var_68]
0x140034901  mov     [rsp+0B8h+dwFlags], r13d; dwFlags
0x140034906  xor     r9d, r9d; pPaddingInfo
0x140034909  mov     [rsp+0B8h+pcbResult], rax; pcbResult
0x14003490e  mov     rdx, r14; pbInput
0x140034911  shl     ebx, 4
0x140034914  mov     [rsp+0B8h+cbOutput], ebx; cbOutput
0x140034918  mov     r8d, ebx; cbInput
0x14003491b  mov     [rsp+0B8h+pbOutput], r15; pbOutput
0x140034920  mov     [rsp+0B8h+cbIV], r13d; cbIV
0x140034925  mov     [rsp+0B8h+pbIV], r13; pbIV
0x14003492a  call    cs:__imp_BCryptEncrypt
0x140034931  nop     dword ptr [rax+rax+00h]
0x140034936  mov     rcx, [rsp+0B8h+var_58]
0x14003493b  xor     rcx, rsp; StackCookie
0x14003493e  call    __security_check_cookie
0x140034943  add     rsp, 78h
0x140034947  pop     r15
0x140034949  pop     r14
0x14003494b  pop     r13
0x14003494d  pop     r12
0x14003494f  pop     rdi
0x140034950  pop     rsi
0x140034951  pop     rbp
0x140034952  pop     rbx
0x140034953  retn
```
