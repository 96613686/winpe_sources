# CPersistStreamInit::WriteVariableColumnDataToStream(void *,CRowInfo &,ushort,tagDBBINDING *)

- ea: `0x18001fff8`
- end: `0x1800201fe`
- name: `?WriteVariableColumnDataToStream@CPersistStreamInit@@AEAAJPEAXAEAVCRowInfo@@GPEAUtagDBBINDING@@@Z`
- size: `518`
- prototype: `__int64 __usercall@<rax>(CPersistStreamInit *__hidden this@<rcx>, void *@<rdx>, struct CRowInfo *@<r8>, unsigned __int16@<r9w>, struct tagDBBINDING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18001d350`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180004384`
- `0x18001b558`
- `0x18001cd30`
- `0x18001fff8`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800200eb`
- `KERNEL32!MultiByteToWideChar` at `0x180020111`
- `KERNEL32!MultiByteToWideChar` at `0x180020167`
- `KERNEL32!MultiByteToWideChar` at `0x1800200eb`
- `KERNEL32!MultiByteToWideChar` at `0x180020111`
- `KERNEL32!MultiByteToWideChar` at `0x180020167`
- `ole32!CoTaskMemFree` at `0x1800201b4`
- `ole32!CoTaskMemFree` at `0x1800201b4`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteVariableColumnDataToStream(
        CPersistStreamInit *this,
        unsigned __int16 *a2,
        struct CRowInfo *a3,
        unsigned __int16 a4,
        struct tagDBBINDING *a5)
{
  __int16 v8; // r10
  unsigned __int16 Type; // r14
  int v10; // r15d
  __int64 cbMaxLen_low; // rbx
  __int16 v13; // r10
  unsigned __int16 v14; // r14
  int v15; // eax
  WCHAR *lpWideCharStr; // rbp
  unsigned int v17; // eax
  unsigned __int16 *v18; // rdx
  unsigned __int128 v19; // rax
  unsigned int v20; // ebx
  int cchWideChar; // [rsp+30h] [rbp-858h]
  WCHAR WideCharStr[1024]; // [rsp+40h] [rbp-848h] BYREF

  Type = CMetaData::mdGetType(a3, a4);
  if ( (v8 & 0x4000) != 0 )
  {
    a2 = *(unsigned __int16 **)a2;
    v10 = 1;
  }
  else
  {
    v10 = 0;
  }
  cbMaxLen_low = *((_QWORD *)a3 + 11);
  if ( *(_DWORD *)(cbMaxLen_low + a5->obStatus) == 4 )
  {
    cbMaxLen_low = LODWORD(a5->cbMaxLen);
    if ( cbMaxLen_low != a5->cbMaxLen )
      return 2147500037LL;
  }
  else
  {
    LODWORD(cbMaxLen_low) = *(_DWORD *)(cbMaxLen_low + a5->obLength);
  }
  v13 = v8 & 0xBFFF;
  v14 = Type & 0xBFFF;
  if ( v13 == 130 )
  {
    v15 = CPersistStreamInit::TextOutW(this, a2, (unsigned int)cbMaxLen_low >> 1, v14);
LABEL_21:
    v20 = v15;
    goto LABEL_22;
  }
  if ( v13 != 129 )
  {
    v15 = CPersistStreamInit::BinaryOut(this, (unsigned __int8 *)a2, cbMaxLen_low);
    goto LABEL_21;
  }
  if ( (unsigned int)(2 * cbMaxLen_low) >= 0x400 )
  {
    cchWideChar = MultiByteToWideChar(0, 0, (LPCCH)a2, cbMaxLen_low, 0, 0);
    v19 = (unsigned int)(cchWideChar + 1) * (unsigned __int128)2uLL;
    if ( !is_mul_ok((unsigned int)(cchWideChar + 1), 2u) )
      LODWORD(v19) = -1;
    lpWideCharStr = (WCHAR *)MMMAlloc(v19, DWORD2(v19));
    if ( !lpWideCharStr )
      return 2147942414LL;
    v17 = MultiByteToWideChar(0, 0, (LPCCH)a2, cbMaxLen_low, lpWideCharStr, cchWideChar);
    v18 = lpWideCharStr;
  }
  else
  {
    lpWideCharStr = 0;
    v17 = MultiByteToWideChar(0, 0, (LPCCH)a2, cbMaxLen_low, WideCharStr, 1024);
    v18 = WideCharStr;
  }
  v20 = CPersistStreamInit::TextOutW(this, v18, v17, v14);
  if ( lpWideCharStr )
    operator delete(lpWideCharStr);
LABEL_22:
  if ( v10 )
  {
    if ( !a5->dwMemOwner )
    {
      CoTaskMemFree(a2);
      *(_QWORD *)(a5->obValue + *((_QWORD *)a3 + 11)) = 0;
    }
  }
  return v20;
}

```

## disassembly

```asm
0x18001fff8  mov     [rsp+arg_18], rbx
0x18001fffd  push    rbp
0x18001fffe  push    rsi
0x18001ffff  push    rdi
0x180020000  push    r12
0x180020002  push    r13
0x180020004  push    r14
0x180020006  push    r15
0x180020008  sub     rsp, 850h
0x18002000f  mov     rax, cs:__security_cookie
0x180020016  xor     rax, rsp
0x180020019  mov     [rsp+888h+var_48], rax
0x180020021  mov     rsi, [rsp+888h+arg_20]
0x180020029  mov     r12, rcx
0x18002002c  mov     rdi, rdx
0x18002002f  mov     rcx, r8; this
0x180020032  movzx   edx, r9w; unsigned __int16
0x180020036  mov     r13, r8
0x180020039  movzx   r10d, word ptr [rsi+54h]
0x18002003e  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180020043  bt      r10w, 0Eh
0x180020049  movzx   r14d, ax
0x18002004d  jnb     short loc_18002005A
0x18002004f  mov     rdi, [rdi]
0x180020052  mov     r15d, 1
0x180020058  jmp     short loc_18002005D
0x18002005a  xor     r15d, r15d
0x18002005d  mov     rbx, [r13+58h]
0x180020061  mov     rax, [rsi+18h]
0x180020065  cmp     dword ptr [rbx+rax], 4
0x180020069  jnz     short loc_18002007E
0x18002006b  mov     ebx, [rsi+48h]
0x18002006e  cmp     rbx, [rsi+48h]
0x180020072  jz      short loc_180020085
0x180020074  mov     eax, 80004005h
0x180020079  jmp     loc_1800201D2
0x18002007e  mov     rax, [rsi+10h]
0x180020082  mov     ebx, [rbx+rax]
0x180020085  mov     eax, 0BFFFh
0x18002008a  and     r10w, ax
0x18002008e  and     r14w, ax
0x180020092  mov     eax, 82h
0x180020097  cmp     r10w, ax
0x18002009b  jnz     short loc_1800200B6
0x18002009d  shr     ebx, 1
0x18002009f  movzx   r9d, r14w; unsigned __int16
0x1800200a3  mov     r8d, ebx; unsigned int
0x1800200a6  mov     rdx, rdi; unsigned __int16 *
0x1800200a9  mov     rcx, r12; this
0x1800200ac  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x1800200b1  jmp     loc_1800201A4
0x1800200b6  mov     eax, 81h
0x1800200bb  cmp     r10w, ax
0x1800200bf  jnz     loc_180020196
0x1800200c5  lea     eax, [rbx+rbx]
0x1800200c8  mov     ecx, 400h
0x1800200cd  xor     edx, edx; dwFlags
0x1800200cf  mov     r9d, ebx; cbMultiByte
0x1800200d2  mov     r8, rdi; lpMultiByteStr
0x1800200d5  cmp     eax, ecx
0x1800200d7  jnb     short loc_1800200FE
0x1800200d9  mov     [rsp+888h+cchWideChar], ecx; cchWideChar
0x1800200dd  lea     rax, [rsp+888h+WideCharStr]
0x1800200e2  xor     ecx, ecx; CodePage
0x1800200e4  mov     [rsp+888h+lpWideCharStr], rax; lpWideCharStr
0x1800200e9  xor     ebp, ebp
0x1800200eb  call    cs:__imp_MultiByteToWideChar
0x1800200f2  nop     dword ptr [rax+rax+00h]
0x1800200f7  lea     rdx, [rsp+888h+WideCharStr]
0x1800200fc  jmp     short loc_180020176
0x1800200fe  mov     [rsp+888h+cchWideChar], 0; cchWideChar
0x180020106  xor     ecx, ecx; CodePage
0x180020108  mov     [rsp+888h+lpWideCharStr], 0; lpWideCharStr
0x180020111  call    cs:__imp_MultiByteToWideChar
0x180020118  nop     dword ptr [rax+rax+00h]
0x18002011d  mov     [rsp+888h+var_858], eax
0x180020121  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020128  lea     edx, [rax+1]; unsigned int
0x18002012b  mov     eax, 2
0x180020130  mul     rdx
0x180020133  cmovb   rax, rcx
0x180020137  mov     ecx, eax; unsigned int
0x180020139  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002013e  mov     rbp, rax
0x180020141  test    rax, rax
0x180020144  jnz     short loc_180020150
0x180020146  mov     eax, 8007000Eh
0x18002014b  jmp     loc_1800201D2
0x180020150  mov     eax, [rsp+888h+var_858]
0x180020154  mov     r9d, ebx; cbMultiByte
0x180020157  mov     [rsp+888h+cchWideChar], eax; cchWideChar
0x18002015b  mov     r8, rdi; lpMultiByteStr
0x18002015e  xor     edx, edx; dwFlags
0x180020160  mov     [rsp+888h+lpWideCharStr], rbp; lpWideCharStr
0x180020165  xor     ecx, ecx; CodePage
0x180020167  call    cs:__imp_MultiByteToWideChar
0x18002016e  nop     dword ptr [rax+rax+00h]
0x180020173  mov     rdx, rbp; unsigned __int16 *
0x180020176  movzx   r9d, r14w; unsigned __int16
0x18002017a  mov     r8d, eax; unsigned int
0x18002017d  mov     rcx, r12; this
0x180020180  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x180020185  mov     ebx, eax
0x180020187  test    rbp, rbp
0x18002018a  jz      short loc_1800201A6
0x18002018c  mov     rcx, rbp; void *
0x18002018f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020194  jmp     short loc_1800201A6
0x180020196  mov     r8d, ebx; unsigned int
0x180020199  mov     rdx, rdi; unsigned __int8 *
0x18002019c  mov     rcx, r12; this
0x18002019f  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x1800201a4  mov     ebx, eax
0x1800201a6  test    r15d, r15d
0x1800201a9  jz      short loc_1800201D0
0x1800201ab  cmp     dword ptr [rsi+3Ch], 0
0x1800201af  jnz     short loc_1800201D0
0x1800201b1  mov     rcx, rdi; pv
0x1800201b4  call    cs:__imp_CoTaskMemFree
0x1800201bb  nop     dword ptr [rax+rax+00h]
0x1800201c0  mov     rcx, [rsi+8]
0x1800201c4  mov     rax, [r13+58h]
0x1800201c8  mov     qword ptr [rcx+rax], 0
0x1800201d0  mov     eax, ebx
0x1800201d2  mov     rcx, [rsp+888h+var_48]
0x1800201da  xor     rcx, rsp; StackCookie
0x1800201dd  call    __security_check_cookie
0x1800201e2  mov     rbx, [rsp+888h+arg_18]
0x1800201ea  add     rsp, 850h
0x1800201f1  pop     r15
0x1800201f3  pop     r14
0x1800201f5  pop     r13
0x1800201f7  pop     r12
0x1800201f9  pop     rdi
0x1800201fa  pop     rsi
0x1800201fb  pop     rbp
0x1800201fc  retn
```
