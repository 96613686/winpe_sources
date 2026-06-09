# CscStorepLowDeleteTree

- ea: `0x14008c4d0`
- end: `0x14008c89c`
- name: `CscStorepLowDeleteTree`
- size: `972`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140017e0c`
- `0x14005cca8`
- `0x140081874`

## callees

- `0x14000b9d0`
- `0x14000cac0`
- `0x14000d780`
- `0x140010e20`
- `0x140017908`
- `0x14002f010`
- `0x14008c4d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008c534`
- `ntoskrnl!ExAllocatePool2` at `0x14008c55d`
- `ntoskrnl!ExAllocatePool2` at `0x14008c726`
- `ntoskrnl!ExAllocatePool2` at `0x14008c534`
- `ntoskrnl!ExAllocatePool2` at `0x14008c55d`
- `ntoskrnl!ExAllocatePool2` at `0x14008c726`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c7ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c852`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c866`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c7ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c852`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c866`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14008c63e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14008c63e`

## pseudocode

```c
__int64 __fastcall CscStorepLowDeleteTree(__int64 a1, const UNICODE_STRING *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r9
  _DWORD *Pool2; // r14
  int InformationFilePoster; // edi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  char v11; // r15
  _QWORD *v12; // rax
  int DirectoryFilePoster; // eax
  __int64 v14; // rdx
  _WORD *v15; // rsi
  USHORT v16; // cx
  _WORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r9
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  _QWORD *v26; // rax
  _QWORD *v27; // rsi
  _QWORD *v28; // rcx
  struct _LIST_ENTRY Handle; // [rsp+70h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+80h] [rbp-19h] BYREF
  int v32[4]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v33; // [rsp+A0h] [rbp+7h]

  Handle.Blink = 0;
  Handle.Flink = 0;
  v33 = 0;
  String2 = 0;
  *(_OWORD *)v32 = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(258, 0x4000, 675312451, a4);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v9 = (_QWORD *)ExAllocatePool2(258, 48, 675312451, v6);
  v10 = v9;
  if ( !v9 )
  {
    InformationFilePoster = -1073741670;
    goto LABEL_45;
  }
  v9[1] = v9;
  v11 = 1;
  *v9 = v9;
  v12 = v9 + 2;
  v12[1] = v12;
  *v12 = v12;
  v10[5] = 0;
  v10[4] = a1;
  while ( 1 )
  {
    LODWORD(Handle.Blink) = 0;
    *Pool2 = 0;
    Pool2[2] = 0;
    DirectoryFilePoster = CscStorepLowIoQueryDirectoryFilePoster(
                            v10[4],
                            (int)Pool2,
                            0x4000,
                            12,
                            0,
                            0,
                            v11,
                            (__int64)&Handle.Blink);
    InformationFilePoster = DirectoryFilePoster;
    v11 = 0;
    if ( DirectoryFilePoster != -2147483642 )
    {
      v15 = Pool2;
      if ( DirectoryFilePoster >= 0 )
        break;
    }
    v25 = 0;
    if ( InformationFilePoster != -2147483642 )
      v25 = InformationFilePoster;
    InformationFilePoster = v25;
    while ( 1 )
    {
      v26 = v10 + 2;
      if ( (_QWORD *)*v26 != v26 )
        break;
      if ( !v10[5] )
      {
        ExFreePoolWithTag(v10, 0x28407343u);
        v10 = 0;
        goto LABEL_41;
      }
      LOBYTE(v14) = 1;
      CscStorepLowIoSetDeleteDisposition(v10[4], v14);
      CscStorepLowIoClose((HANDLE)v10[4]);
      v27 = (_QWORD *)v10[5];
      v10[4] = 0;
      ExFreePoolWithTag(v10, 0x28407343u);
      v10 = v27;
      if ( !v27 )
        goto LABEL_41;
    }
    v10 = (_QWORD *)v10[3];
    if ( (_QWORD *)*v10 != v26 || (v28 = (_QWORD *)v10[1], (_QWORD *)*v28 != v10) )
LABEL_47:
      __fastfail(3u);
    v26[1] = v28;
    v11 = 1;
    *v28 = v26;
LABEL_41:
    if ( !v10 )
      goto LABEL_45;
  }
  while ( *((_DWORD *)v15 + 2) <= 0x3FF0u )
  {
    v16 = v15[4];
    v17 = v15 + 6;
    String2.Length = v16;
    String2.MaximumLength = v16;
    String2.Buffer = v15 + 6;
    if ( v16 == 2 )
    {
      if ( *v17 == 46 )
        goto LABEL_28;
    }
    else if ( v16 == 4 && *v17 == 46 && v15[7] == 46 )
    {
      goto LABEL_28;
    }
    if ( !a2 || v10[5] || !RtlEqualUnicodeString(a2, &String2, 1u) )
    {
      Handle.Flink = 0;
      InformationFilePoster = CscStorepLowIoCreateFilePoster(
                                &Handle,
                                (struct _LIST_ENTRY *)v10[4],
                                (struct _LIST_ENTRY *)&String2,
                                1114240,
                                0,
                                0,
                                7,
                                1,
                                32,
                                0,
                                0,
                                0,
                                0);
      if ( InformationFilePoster >= 0 )
      {
        InformationFilePoster = CscStorepLowIoQueryInformationFilePoster(
                                  (int)Handle.Flink,
                                  (int)v32,
                                  24,
                                  5,
                                  (unsigned __int64)&Handle.Blink + 4);
        if ( InformationFilePoster >= 0 )
        {
          if ( BYTE5(v33) )
          {
            v20 = (_QWORD *)ExAllocatePool2(258, 48, 675312451, v19);
            v21 = v20;
            if ( v20 )
            {
              v20[1] = v20;
              *v20 = v20;
              v22 = v20 + 2;
              v21[3] = v22;
              *v22 = v22;
              v21[5] = v10;
              v21[4] = Handle.Flink;
              Handle.Flink = 0;
              v23 = (_QWORD *)v10[3];
              if ( (_QWORD *)*v23 != v10 + 2 )
                goto LABEL_47;
              *v21 = v10 + 2;
              InformationFilePoster = 0;
              v21[1] = v23;
              *v23 = v21;
              v10[3] = v21;
            }
            else
            {
              InformationFilePoster = -1073741670;
            }
          }
          else
          {
            LOBYTE(v18) = 1;
            CscStorepLowIoSetDeleteDisposition(Handle.Flink, v18);
          }
        }
        if ( Handle.Flink )
        {
          CscStorepLowIoClose(Handle.Flink);
          Handle.Flink = 0;
        }
      }
    }
LABEL_28:
    v24 = *(unsigned int *)v15;
    if ( !(_DWORD)v24 )
      goto LABEL_41;
    v15 = (_WORD *)((char *)v15 + v24);
  }
  InformationFilePoster = -1073741789;
  if ( v10 )
    ExFreePoolWithTag(v10, 0x28407343u);
LABEL_45:
  ExFreePoolWithTag(Pool2, 0x28407343u);
  return (unsigned int)InformationFilePoster;
}

```

## disassembly

```asm
0x14008c4d0  push    rbp
0x14008c4d2  push    rbx
0x14008c4d3  push    rsi
0x14008c4d4  push    rdi
0x14008c4d5  push    r12
0x14008c4d7  push    r13
0x14008c4d9  push    r14
0x14008c4db  push    r15
0x14008c4dd  lea     rbp, [rsp-1Fh]
0x14008c4e2  sub     rsp, 0B8h
0x14008c4e9  mov     rax, cs:__security_cookie
0x14008c4f0  xor     rax, rsp
0x14008c4f3  mov     [rbp+57h+var_48], rax
0x14008c4f7  xor     r13d, r13d
0x14008c4fa  mov     r12, rdx
0x14008c4fd  mov     rdi, rcx
0x14008c500  mov     dword ptr [rbp+57h+var_78], r13d
0x14008c504  xorps   xmm0, xmm0
0x14008c507  mov     [rbp+57h+Handle], r13
0x14008c50b  xorps   xmm1, xmm1
0x14008c50e  mov     dword ptr [rbp+57h+var_78+4], r13d
0x14008c512  xor     eax, eax
0x14008c514  mov     ebx, 28407343h
0x14008c519  mov     esi, 102h
0x14008c51e  mov     [rbp+57h+var_50], rax
0x14008c522  mov     r8d, ebx
0x14008c525  mov     ecx, esi
0x14008c527  mov     edx, 4000h
0x14008c52c  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x14008c530  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x14008c534  call    cs:__imp_ExAllocatePool2
0x14008c53b  nop     dword ptr [rax+rax+00h]
0x14008c540  mov     r14, rax
0x14008c543  test    rax, rax
0x14008c546  jnz     short loc_14008C552
0x14008c548  mov     edi, 0C000009Ah
0x14008c54d  jmp     loc_14008C872
0x14008c552  mov     r8d, ebx
0x14008c555  mov     edx, 30h ; '0'
0x14008c55a  mov     rcx, rsi
0x14008c55d  call    cs:__imp_ExAllocatePool2
0x14008c564  nop     dword ptr [rax+rax+00h]
0x14008c569  mov     rbx, rax
0x14008c56c  test    rax, rax
0x14008c56f  jnz     short loc_14008C57B
0x14008c571  mov     edi, 0C000009Ah
0x14008c576  jmp     loc_14008C85E
0x14008c57b  mov     [rax+8], rbx
0x14008c57f  mov     r15b, 1
0x14008c582  mov     [rax], rbx
0x14008c585  add     rax, 10h
0x14008c589  mov     [rax+8], rax
0x14008c58d  mov     [rax], rax
0x14008c590  mov     [rbx+28h], r13
0x14008c594  mov     [rbx+20h], rdi
0x14008c598  mov     dword ptr [rbp+57h+var_78], r13d
0x14008c59c  lea     rax, [rbp+57h+var_78]
0x14008c5a0  mov     [rsp+0F0h+var_B8], rax; __int64
0x14008c5a5  mov     r9d, 0Ch; int
0x14008c5ab  mov     [rsp+0F0h+var_C0], r15b; char
0x14008c5b0  mov     r8d, 4000h; int
0x14008c5b6  mov     [r14], r13d
0x14008c5b9  mov     rdx, r14; int
0x14008c5bc  mov     [r14+8], r13d
0x14008c5c0  mov     rcx, [rbx+20h]; int
0x14008c5c4  mov     [rsp+0F0h+LowLimit], r13; LowLimit
0x14008c5c9  mov     [rsp+0F0h+var_D0], r13b; char
0x14008c5ce  call    CscStorepLowIoQueryDirectoryFilePoster
0x14008c5d3  mov     edi, eax
0x14008c5d5  mov     r15b, r13b
0x14008c5d8  cmp     eax, 80000006h
0x14008c5dd  jz      loc_14008C7A9
0x14008c5e3  mov     rsi, r14
0x14008c5e6  test    eax, eax
0x14008c5e8  js      loc_14008C7A9
0x14008c5ee  cmp     dword ptr [rsi+8], 3FF0h
0x14008c5f5  ja      loc_14008C840
0x14008c5fb  movzx   ecx, word ptr [rsi+8]
0x14008c5ff  lea     rax, [rsi+0Ch]
0x14008c603  mov     edx, 2
0x14008c608  mov     [rbp+57h+String2.Length], cx
0x14008c60c  mov     [rbp+57h+String2.MaximumLength], cx
0x14008c610  mov     [rbp+57h+String2.Buffer], rax
0x14008c614  cmp     dx, cx
0x14008c617  jnz     loc_14008C6ED
0x14008c61d  lea     ecx, [rdx+2Ch]
0x14008c620  cmp     cx, [rax]
0x14008c623  jz      loc_14008C797
0x14008c629  test    r12, r12
0x14008c62c  jz      short loc_14008C652
0x14008c62e  cmp     [rbx+28h], r13
0x14008c632  jnz     short loc_14008C652
0x14008c634  mov     r8b, 1; CaseInSensitive
0x14008c637  lea     rdx, [rbp+57h+String2]; String2
0x14008c63b  mov     rcx, r12; String1
0x14008c63e  call    cs:__imp_RtlEqualUnicodeString
0x14008c645  nop     dword ptr [rax+rax+00h]
0x14008c64a  test    al, al
0x14008c64c  jnz     loc_14008C797
0x14008c652  mov     [rsp+0F0h+var_90], r13
0x14008c657  lea     r8, [rbp+57h+String2]
0x14008c65b  mov     [rsp+0F0h+var_98], r13
0x14008c660  lea     rcx, [rbp+57h+Handle]
0x14008c664  mov     [rsp+0F0h+var_A0], r13d
0x14008c669  mov     r9d, 110080h
0x14008c66f  mov     [rsp+0F0h+var_A8], r13
0x14008c674  mov     [rsp+0F0h+var_B0], 20h ; ' '
0x14008c67c  mov     dword ptr [rsp+0F0h+var_B8], 1
0x14008c684  mov     dword ptr [rsp+0F0h+var_C0], 7
0x14008c68c  mov     [rbp+57h+Handle], r13
0x14008c690  mov     rdx, [rbx+20h]
0x14008c694  mov     dword ptr [rsp+0F0h+LowLimit], r13d
0x14008c699  mov     qword ptr [rsp+0F0h+var_D0], r13
0x14008c69e  call    CscStorepLowIoCreateFilePoster
0x14008c6a3  mov     edi, eax
0x14008c6a5  test    eax, eax
0x14008c6a7  js      loc_14008C797
0x14008c6ad  mov     rcx, [rbp+57h+Handle]; int
0x14008c6b1  lea     rax, [rbp+57h+var_78+4]
0x14008c6b5  mov     r9d, 5; int
0x14008c6bb  mov     qword ptr [rsp+0F0h+var_D0], rax; LowLimit
0x14008c6c0  lea     rdx, [rbp+57h+var_60]; int
0x14008c6c4  lea     r8d, [r9+13h]; int
0x14008c6c8  call    CscStorepLowIoQueryInformationFilePoster
0x14008c6cd  mov     edi, eax
0x14008c6cf  test    eax, eax
0x14008c6d1  js      loc_14008C785
0x14008c6d7  cmp     byte ptr [rbp+57h+var_50+5], r13b
0x14008c6db  jnz     short loc_14008C716
0x14008c6dd  mov     rcx, [rbp+57h+Handle]
0x14008c6e1  mov     dl, 1
0x14008c6e3  call    CscStorepLowIoSetDeleteDisposition
0x14008c6e8  jmp     loc_14008C785
0x14008c6ed  mov     edx, 4
0x14008c6f2  cmp     dx, cx
0x14008c6f5  jnz     loc_14008C629
0x14008c6fb  lea     ecx, [rdx+2Ah]
0x14008c6fe  cmp     cx, [rax]
0x14008c701  jnz     loc_14008C629
0x14008c707  cmp     cx, [rax+2]
0x14008c70b  jz      loc_14008C797
0x14008c711  jmp     loc_14008C629
0x14008c716  mov     edx, 30h ; '0'
0x14008c71b  mov     ecx, 102h
0x14008c720  mov     r8d, 28407343h
0x14008c726  call    cs:__imp_ExAllocatePool2
0x14008c72d  nop     dword ptr [rax+rax+00h]
0x14008c732  mov     rcx, rax
0x14008c735  test    rax, rax
0x14008c738  jnz     short loc_14008C741
0x14008c73a  mov     edi, 0C000009Ah
0x14008c73f  jmp     short loc_14008C785
0x14008c741  mov     [rax+8], rcx
0x14008c745  mov     [rax], rcx
0x14008c748  add     rax, 10h
0x14008c74c  mov     [rcx+18h], rax
0x14008c750  mov     [rax], rax
0x14008c753  mov     [rcx+28h], rbx
0x14008c757  mov     rax, [rbp+57h+Handle]
0x14008c75b  mov     [rcx+20h], rax
0x14008c75f  lea     rax, [rbx+10h]
0x14008c763  mov     [rbp+57h+Handle], r13
0x14008c767  mov     rdx, [rax+8]
0x14008c76b  cmp     [rdx], rax
0x14008c76e  jnz     loc_14008C895
0x14008c774  mov     [rcx], rax
0x14008c777  mov     edi, r13d
0x14008c77a  mov     [rcx+8], rdx
0x14008c77e  mov     [rdx], rcx
0x14008c781  mov     [rax+8], rcx
0x14008c785  mov     rcx, [rbp+57h+Handle]; Handle
0x14008c789  test    rcx, rcx
0x14008c78c  jz      short loc_14008C797
0x14008c78e  call    CscStorepLowIoClose
0x14008c793  mov     [rbp+57h+Handle], r13
0x14008c797  mov     eax, [rsi]
0x14008c799  test    eax, eax
0x14008c79b  jz      loc_14008C835
0x14008c7a1  add     rsi, rax
0x14008c7a4  jmp     loc_14008C5EE
0x14008c7a9  cmp     edi, 80000006h
0x14008c7af  mov     eax, r13d
0x14008c7b2  cmovnz  eax, edi
0x14008c7b5  mov     edi, eax
0x14008c7b7  lea     rax, [rbx+10h]
0x14008c7bb  cmp     [rax], rax
0x14008c7be  jnz     short loc_14008C819
0x14008c7c0  cmp     [rbx+28h], r13
0x14008c7c4  jz      short loc_14008C800
0x14008c7c6  mov     rcx, [rbx+20h]
0x14008c7ca  mov     dl, 1
0x14008c7cc  call    CscStorepLowIoSetDeleteDisposition
0x14008c7d1  mov     rcx, [rbx+20h]; Handle
0x14008c7d5  call    CscStorepLowIoClose
0x14008c7da  mov     rsi, [rbx+28h]
0x14008c7de  mov     edx, 28407343h; Tag
0x14008c7e3  mov     rcx, rbx; P
0x14008c7e6  mov     [rbx+20h], r13
0x14008c7ea  call    cs:__imp_ExFreePoolWithTag
0x14008c7f1  nop     dword ptr [rax+rax+00h]
0x14008c7f6  mov     rbx, rsi
0x14008c7f9  test    rsi, rsi
0x14008c7fc  jz      short loc_14008C835
0x14008c7fe  jmp     short loc_14008C7B7
0x14008c800  mov     edx, 28407343h; Tag
0x14008c805  mov     rcx, rbx; P
0x14008c808  call    cs:__imp_ExFreePoolWithTag
0x14008c80f  nop     dword ptr [rax+rax+00h]
0x14008c814  mov     rbx, r13
0x14008c817  jmp     short loc_14008C835
0x14008c819  mov     rbx, [rax+8]
0x14008c81d  cmp     [rbx], rax
0x14008c820  jnz     short loc_14008C895
0x14008c822  mov     rcx, [rbx+8]
0x14008c826  cmp     [rcx], rbx
0x14008c829  jnz     short loc_14008C895
0x14008c82b  mov     [rax+8], rcx
0x14008c82f  mov     r15b, 1
0x14008c832  mov     [rcx], rax
0x14008c835  test    rbx, rbx
0x14008c838  jnz     loc_14008C598
0x14008c83e  jmp     short loc_14008C85E
0x14008c840  mov     edi, 0C0000023h
0x14008c845  test    rbx, rbx
0x14008c848  jz      short loc_14008C85E
0x14008c84a  mov     edx, 28407343h; Tag
0x14008c84f  mov     rcx, rbx; P
0x14008c852  call    cs:__imp_ExFreePoolWithTag
0x14008c859  nop     dword ptr [rax+rax+00h]
0x14008c85e  mov     edx, 28407343h; Tag
0x14008c863  mov     rcx, r14; P
0x14008c866  call    cs:__imp_ExFreePoolWithTag
0x14008c86d  nop     dword ptr [rax+rax+00h]
0x14008c872  mov     eax, edi
0x14008c874  mov     rcx, [rbp+57h+var_48]
0x14008c878  xor     rcx, rsp; StackCookie
0x14008c87b  call    __security_check_cookie
0x14008c880  add     rsp, 0B8h
0x14008c887  pop     r15
0x14008c889  pop     r14
0x14008c88b  pop     r13
0x14008c88d  pop     r12
0x14008c88f  pop     rdi
0x14008c890  pop     rsi
0x14008c891  pop     rbx
0x14008c892  pop     rbp
0x14008c893  retn
0x14008c895  mov     ecx, 3
0x14008c89a  int     29h; Win8: RtlFailFast(ecx)
```
