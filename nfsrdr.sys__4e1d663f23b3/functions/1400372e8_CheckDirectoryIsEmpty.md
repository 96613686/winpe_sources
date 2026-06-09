# CheckDirectoryIsEmpty

- ea: `0x1400372e8`
- end: `0x1400374f0`
- name: `CheckDirectoryIsEmpty`
- size: `520`
- prototype: `__int64 __fastcall(__int64, int, int, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001b1c4`

## callees

- `0x140013dc0`
- `0x140014970`
- `0x1400159cc`
- `0x1400372e8`
- `0x14003aba0`

## pseudocode

```c
__int64 __fastcall CheckDirectoryIsEmpty(__int64 a1, int a2, int a3, _BYTE *a4)
{
  int v7; // edi
  __int64 v8; // rdx
  bool v9; // zf
  __int64 result; // rax
  int DirectoryEntry; // ebx
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v13; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v14; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v16[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h]
  __int16 v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  __int64 v20; // [rsp+88h] [rbp-78h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+A0h] [rbp-60h]
  __int64 v23; // [rsp+A8h] [rbp-58h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  int v26; // [rsp+C8h] [rbp-38h]
  char *v27; // [rsp+170h] [rbp+70h]
  char v28; // [rsp+178h] [rbp+78h] BYREF

  v14 = 0;
  v15 = 0;
  v12 = 0;
  v7 = a1;
  *a4 = 0;
  if ( !a1 )
    return 3221225473LL;
  v8 = *(_QWORD *)(a1 + 40);
  if ( !v8 )
    return 3221225473LL;
  v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL) + 88LL) == 2;
  v16[1] = *(_DWORD *)(v8 + 24);
  v13 = v16;
  v16[0] = !v9 + 1;
  v27 = &v28;
  v18 = -1;
  v26 = 0;
  v19 = -1;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  v25 = 0;
  v24 = 0;
  v22 = 7;
  v23 = 0;
  result = NfsReadDirectoryEntry(a1, a2, a3, (unsigned int)&v13, 0, (__int64)&v15, (__int64)&v14, (__int64)&v12, 0, 0);
  if ( (int)result >= 0 )
  {
    do
    {
      if ( (v12 != 1 || *v14 != 46) && (v12 != 2 || *v14 != 46 || v14[1] != 46) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
        }
        NfsReadDirectoryQuit(&v13, 0);
        return 0;
      }
      DirectoryEntry = NfsReadDirectoryEntry(
                         v7,
                         a2,
                         a3,
                         (unsigned int)&v13,
                         0,
                         (__int64)&v15,
                         (__int64)&v14,
                         (__int64)&v12,
                         0,
                         0);
    }
    while ( DirectoryEntry >= 0 );
    NfsReadDirectoryQuit(&v13, 0);
    if ( DirectoryEntry == -2147483642 )
      goto LABEL_13;
    return (unsigned int)DirectoryEntry;
  }
  else if ( (_DWORD)result == -2147483642 )
  {
LABEL_13:
    *a4 = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400372e8  push    rbp
0x1400372ea  push    rbx
0x1400372eb  push    rsi
0x1400372ec  push    rdi
0x1400372ed  push    r12
0x1400372ef  push    r14
0x1400372f1  push    r15
0x1400372f3  lea     rbp, [rsp-190h]
0x1400372fb  sub     rsp, 290h
0x140037302  mov     rax, cs:__security_cookie
0x140037309  xor     rax, rsp
0x14003730c  mov     [rbp+1C0h+var_40], rax
0x140037313  xor     r12d, r12d
0x140037316  mov     rsi, r9
0x140037319  mov     [rsp+2C0h+var_260], r12
0x14003731e  mov     r15, r8
0x140037321  mov     [rsp+2C0h+var_258], r12
0x140037326  mov     r14, rdx
0x140037329  mov     [rsp+2C0h+var_270], r12d
0x14003732e  mov     rdi, rcx
0x140037331  mov     [r9], r12b
0x140037334  test    rcx, rcx
0x140037337  jz      loc_1400374C9
0x14003733d  mov     rdx, [rcx+28h]
0x140037341  test    rdx, rdx
0x140037344  jz      loc_1400374C9
0x14003734a  mov     rax, [rcx+20h]
0x14003734e  lea     r9, [rsp+2C0h+var_268]
0x140037353  mov     [rsp+2C0h+var_278], r12
0x140037358  mov     [rsp+2C0h+var_280], r12
0x14003735d  mov     rcx, [rax+20h]
0x140037361  mov     rax, [rcx+20h]
0x140037365  mov     ecx, r12d
0x140037368  cmp     dword ptr [rax+58h], 2
0x14003736c  mov     eax, [rdx+18h]
0x14003736f  lea     rdx, [rsp+2C0h+var_250]
0x140037374  mov     [rsp+2C0h+var_24C], eax
0x140037378  setnz   cl
0x14003737b  inc     ecx
0x14003737d  mov     [rsp+2C0h+var_268], rdx
0x140037382  mov     [rsp+2C0h+var_250], ecx
0x140037386  lea     rax, [rsp+2C0h+var_270]
0x14003738b  mov     [rsp+2C0h+var_288], rax
0x140037390  lea     rdx, [rbp+1C0h+var_148]
0x140037394  lea     rax, [rsp+2C0h+var_260]
0x140037399  mov     [rbp+1C0h+var_150], rdx
0x14003739d  mov     [rsp+2C0h+var_290], rax
0x1400373a2  mov     ecx, 0FFFFh
0x1400373a7  lea     rax, [rsp+2C0h+var_258]
0x1400373ac  mov     [rbp+1C0h+var_240], cx
0x1400373b0  mov     [rsp+2C0h+var_298], rax
0x1400373b5  mov     rcx, rdi
0x1400373b8  mov     rdx, r14
0x1400373bb  mov     [rsp+2C0h+var_2A0], r12b
0x1400373c0  mov     [rbp+1C0h+var_1F8], r12d
0x1400373c4  mov     [rbp+1C0h+var_23C], 0FFFFFFFFh
0x1400373cb  mov     [rbp+1C0h+var_238], r12
0x1400373cf  mov     [rbp+1C0h+var_230], r12
0x1400373d3  mov     [rsp+2C0h+var_248], r12
0x1400373d8  mov     [rbp+1C0h+var_200], r12
0x1400373dc  mov     [rbp+1C0h+var_210], r12
0x1400373e0  mov     [rbp+1C0h+var_220], 7
0x1400373e7  mov     [rbp+1C0h+var_218], r12
0x1400373eb  call    NfsReadDirectoryEntry
0x1400373f0  test    eax, eax
0x1400373f2  jns     short loc_140037404
0x1400373f4  cmp     eax, 80000006h
0x1400373f9  jz      loc_140037481
0x1400373ff  jmp     loc_1400374CE
0x140037404  cmp     [rsp+2C0h+var_270], 1
0x140037409  mov     rax, [rsp+2C0h+var_260]
0x14003740e  jnz     short loc_140037415
0x140037410  cmp     byte ptr [rax], 2Eh ; '.'
0x140037413  jz      short loc_140037427
0x140037415  cmp     [rsp+2C0h+var_270], 2
0x14003741a  jnz     short loc_14003748C
0x14003741c  cmp     byte ptr [rax], 2Eh ; '.'
0x14003741f  jnz     short loc_14003748C
0x140037421  cmp     byte ptr [rax+1], 2Eh ; '.'
0x140037425  jnz     short loc_14003748C
0x140037427  mov     [rsp+2C0h+var_278], r12
0x14003742c  lea     rax, [rsp+2C0h+var_270]
0x140037431  mov     [rsp+2C0h+var_280], r12
0x140037436  lea     r9, [rsp+2C0h+var_268]
0x14003743b  mov     [rsp+2C0h+var_288], rax
0x140037440  mov     r8, r15
0x140037443  lea     rax, [rsp+2C0h+var_260]
0x140037448  mov     rdx, r14
0x14003744b  mov     [rsp+2C0h+var_290], rax
0x140037450  mov     rcx, rdi
0x140037453  lea     rax, [rsp+2C0h+var_258]
0x140037458  mov     [rsp+2C0h+var_298], rax
0x14003745d  mov     [rsp+2C0h+var_2A0], r12b
0x140037462  call    NfsReadDirectoryEntry
0x140037467  mov     ebx, eax
0x140037469  test    eax, eax
0x14003746b  jns     short loc_140037404
0x14003746d  xor     edx, edx
0x14003746f  lea     rcx, [rsp+2C0h+var_268]
0x140037474  call    NfsReadDirectoryQuit
0x140037479  cmp     ebx, 80000006h
0x14003747f  jnz     short loc_140037488
0x140037481  mov     byte ptr [rsi], 1
0x140037484  xor     eax, eax
0x140037486  jmp     short loc_1400374CE
0x140037488  mov     eax, ebx
0x14003748a  jmp     short loc_1400374CE
0x14003748c  mov     rcx, cs:WPP_GLOBAL_Control
0x140037493  lea     rax, WPP_GLOBAL_Control
0x14003749a  cmp     rcx, rax
0x14003749d  jz      short loc_1400374BB
0x14003749f  mov     eax, [rcx+2Ch]
0x1400374a2  test    al, 20h
0x1400374a4  jz      short loc_1400374BB
0x1400374a6  mov     rcx, [rcx+18h]
0x1400374aa  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x1400374b1  mov     edx, 19h
0x1400374b6  call    WPP_SF_
0x1400374bb  xor     edx, edx
0x1400374bd  lea     rcx, [rsp+2C0h+var_268]
0x1400374c2  call    NfsReadDirectoryQuit
0x1400374c7  jmp     short loc_140037484
0x1400374c9  mov     eax, 0C0000001h
0x1400374ce  mov     rcx, [rbp+1C0h+var_40]
0x1400374d5  xor     rcx, rsp; StackCookie
0x1400374d8  call    __security_check_cookie
0x1400374dd  add     rsp, 290h
0x1400374e4  pop     r15
0x1400374e6  pop     r14
0x1400374e8  pop     r12
0x1400374ea  pop     rdi
0x1400374eb  pop     rsi
0x1400374ec  pop     rbx
0x1400374ed  pop     rbp
0x1400374ee  retn
```
