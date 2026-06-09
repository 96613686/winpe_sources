# PssNtWin32LiveSystemProvider::EnumHandleObjectInfo(unsigned __int64,ushort const *,ulong,ulong *,void *,ulong,ulong *)

- ea: `0x180020730`
- end: `0x180020b7e`
- name: `?EnumHandleObjectInfo@PssNtWin32LiveSystemProvider@@UEAAJ_KPEBGKPEAKPEAXK2@Z`
- size: `1102`
- prototype: `int(PssNtWin32LiveSystemProvider *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned int, unsigned int *, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180020730`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800208ab`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800208d6`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x18002093c`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800209cd`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180020a5d`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180020aa8`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180020aed`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800208ab`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800208d6`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x18002093c`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x1800209cd`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180020a5d`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180020aa8`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180020aed`

## string_xrefs

- `0x180020932`: `Thread`

## pseudocode

```c
__int64 __fastcall PssNtWin32LiveSystemProvider::EnumHandleObjectInfo(
        PssNtWin32LiveSystemProvider *this,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5,
        _DWORD *a6,
        unsigned int a7,
        unsigned int *a8)
{
  __int64 result; // rax
  bool v13; // cc
  int v14; // esi
  unsigned int v15; // ebx
  bool v16; // zf
  int v17; // ebx
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  int v21; // ebx
  int v22; // eax
  int v23; // eax
  _DWORD *v24; // rax
  __int64 v25; // [rsp+30h] [rbp-B9h] BYREF
  __int64 v26; // [rsp+38h] [rbp-B1h] BYREF
  __int64 v27; // [rsp+40h] [rbp-A9h] BYREF
  unsigned int *v28; // [rsp+48h] [rbp-A1h]
  __int64 v29; // [rsp+50h] [rbp-99h] BYREF
  char v30; // [rsp+58h] [rbp-91h]
  int v31; // [rsp+5Ch] [rbp-8Dh]
  __int16 v32; // [rsp+88h] [rbp-61h]
  LPCWSTR lpString1; // [rsp+90h] [rbp-59h]
  __int64 v34; // [rsp+A8h] [rbp-41h]
  __int64 v35; // [rsp+B0h] [rbp-39h]
  __int64 v36; // [rsp+B8h] [rbp-31h]
  __int64 v37; // [rsp+C0h] [rbp-29h]
  unsigned int v38; // [rsp+C8h] [rbp-21h]
  int v39; // [rsp+CCh] [rbp-1Dh]

  v28 = a5;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  memset_0(&v29, 0, 0x88u);
  *a8 = 0;
  result = (*((__int64 (__fastcall **)(_QWORD, __int64 *))this + 146))(*((_QWORD *)this + 156), &v26);
  v13 = (int)result <= 0;
  if ( (_DWORD)result )
  {
LABEL_6:
    if ( !v13 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v14 = 2;
  while ( 1 )
  {
    result = (*((__int64 (__fastcall **)(_QWORD, __int64 *))this + 146))(*((_QWORD *)this + 156), &v27);
    v13 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_6;
    result = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *, int))this + 143))(
               *((_QWORD *)this + 153),
               2,
               *((_QWORD *)this + 156),
               &v29,
               136);
    if ( (_DWORD)result != 259 )
      break;
    result = (*((__int64 (__fastcall **)(_QWORD))this + 148))(*((_QWORD *)this + 156));
    v13 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_6;
LABEL_11:
    result = (*((__int64 (__fastcall **)(_QWORD, __int64 *))this + 146))(*((_QWORD *)this + 156), &v25);
    v13 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_6;
    if ( v26 == v25 )
      return 3489661477LL;
  }
  v13 = (int)result <= 0;
  if ( (_DWORD)result )
    goto LABEL_6;
  if ( v29 != a2 )
    goto LABEL_11;
  if ( !v32 || !lpString1 || lstrcmpiW(lpString1, a3) )
    return 3489660964LL;
  v15 = 8;
  if ( (v30 & 8) == 0 )
    return 2147943568LL;
  if ( lstrcmpiW(a3, L"Mutant") )
  {
    if ( !lstrcmpiW(a3, L"Thread") )
    {
      if ( !a4 )
      {
        if ( a7 < 0x30 )
          return 3489660932LL;
        a6[1] = 0;
        v17 = 16;
        v18 = v38;
        *a6 = v34;
        *((_QWORD *)a6 + 1) = v35;
        *((_QWORD *)a6 + 2) = (unsigned int)v36;
        *((_QWORD *)a6 + 3) = HIDWORD(v36);
        *((_QWORD *)a6 + 4) = v37;
        if ( v18 == -15 )
        {
          v19 = -16;
        }
        else
        {
          v19 = 16;
          if ( v18 != 15 )
            v19 = v18;
        }
        a6[10] = v19;
        if ( v39 == -15 )
        {
          v17 = -16;
        }
        else if ( v39 != 15 )
        {
          v17 = v39;
        }
        v14 = 1;
        a6[11] = v17;
        v15 = 48;
        goto LABEL_70;
      }
      return 1;
    }
    if ( !lstrcmpiW(a3, L"Process") )
    {
      if ( a4 >= 4 )
        return 3489660931LL;
      if ( a4 )
        return 1;
      if ( a7 < 0x40 )
        return 3489660932LL;
      a6[3] = 0;
      a6[9] = 0;
      a6[15] = 0;
      a6[2] = v34;
      *((_QWORD *)a6 + 2) = v35;
      *((_QWORD *)a6 + 3) = v36;
      v20 = v37;
      *(_QWORD *)a6 = 64;
      if ( v20 == -15 )
      {
        v21 = -16;
      }
      else
      {
        v21 = 16;
        if ( v20 != 15 )
          v21 = v20;
      }
      v14 = 5;
      *((_QWORD *)a6 + 5) = HIDWORD(v37);
      *((_QWORD *)a6 + 6) = v38;
      v22 = v39;
      a6[8] = v21;
      v15 = 64;
      a6[14] = v22;
LABEL_70:
      v24 = v28;
      *a8 = v15;
      *v24 = v14;
      result = (*((__int64 (__fastcall **)(_QWORD, __int64))this + 147))(*((_QWORD *)this + 156), v27);
      v13 = (int)result <= 0;
      if ( !(_DWORD)result )
        return result;
      goto LABEL_6;
    }
    if ( !lstrcmpiW(a3, L"Event") )
    {
      v14 = 6;
      if ( a4 >= 6 )
        return 3489660931LL;
      if ( a4 )
        return 1;
      if ( a7 < 8 )
        return 3489660932LL;
      v16 = HIDWORD(v34) == 0;
      *a6 = v34 == 0;
      v23 = !v16;
LABEL_69:
      a6[1] = v23;
      goto LABEL_70;
    }
    if ( !lstrcmpiW(a3, L"Section") )
    {
      v14 = 7;
      if ( a4 >= 7 )
        return 3489660931LL;
      if ( a4 )
        return 1;
      v15 = 24;
      if ( a7 < 0x18 )
        return 3489660932LL;
      a6[3] = 0;
      *(_QWORD *)a6 = v34;
      a6[2] = v35;
      *((_QWORD *)a6 + 2) = v36;
      goto LABEL_70;
    }
    if ( lstrcmpiW(a3, L"Semaphore") )
      return 2147942450LL;
    if ( v31 == 6 )
    {
      if ( a4 >= 8 )
        return 3489660931LL;
      if ( a4 )
        return 1;
      if ( a7 < 8 )
        return 3489660932LL;
      v14 = 8;
      *a6 = v34;
      v23 = HIDWORD(v34);
      goto LABEL_69;
    }
    return 3489660964LL;
  }
  if ( !a4 )
  {
    if ( a7 < 8 )
      return 3489660932LL;
    v16 = HIDWORD(v34) == 0;
    *(_QWORD *)a6 = 0;
    *a6 = v34;
    *((_BYTE *)a6 + 5) = !v16;
    goto LABEL_70;
  }
  if ( a4 != 2 )
    return 3489660931LL;
  v15 = 16;
  if ( a7 >= 0x10 )
  {
    v14 = 3;
    *(_QWORD *)a6 = (unsigned int)v35;
    *((_QWORD *)a6 + 1) = HIDWORD(v35);
    goto LABEL_70;
  }
  return 3489660932LL;
}

```

## disassembly

```asm
0x180020730  mov     [rsp-8+arg_8], rbx
0x180020735  push    rbp
0x180020736  push    rsi
0x180020737  push    rdi
0x180020738  push    r12
0x18002073a  push    r13
0x18002073c  push    r14
0x18002073e  push    r15
0x180020740  lea     rbp, [rsp-7]
0x180020745  sub     rsp, 0F0h
0x18002074c  mov     rax, cs:__security_cookie
0x180020753  xor     rax, rsp
0x180020756  mov     [rbp+37h+var_40], rax
0x18002075a  mov     rax, [rbp+37h+arg_20]
0x18002075e  xor     esi, esi
0x180020760  mov     rdi, [rbp+37h+arg_28]
0x180020764  mov     r15, r8
0x180020767  mov     r12, [rbp+37h+arg_38]
0x18002076b  mov     rbx, rdx
0x18002076e  mov     r13, rcx
0x180020771  mov     [rsp+120h+var_D8], rax
0x180020776  xor     edx, edx; Val
0x180020778  mov     [rsp+120h+var_E8], rsi
0x18002077d  mov     r8d, 88h; Size
0x180020783  mov     [rsp+120h+var_E0], rsi
0x180020788  lea     rcx, [rsp+120h+var_D0]; void *
0x18002078d  mov     [rsp+120h+var_F0], rsi
0x180020792  mov     r14d, r9d
0x180020795  call    memset_0
0x18002079a  mov     [r12], esi
0x18002079e  lea     rdx, [rsp+120h+var_E8]
0x1800207a3  mov     rcx, [r13+4E0h]
0x1800207aa  mov     rax, [r13+490h]
0x1800207b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b6  test    eax, eax
0x1800207b8  jnz     short loc_180020820
0x1800207ba  lea     esi, [rax+2]
0x1800207bd  mov     rcx, [r13+4E0h]
0x1800207c4  lea     rdx, [rsp+120h+var_E0]
0x1800207c9  mov     rax, [r13+490h]
0x1800207d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207d5  test    eax, eax
0x1800207d7  jnz     short loc_180020820
0x1800207d9  mov     r8, [r13+4E0h]
0x1800207e0  lea     r9, [rsp+120h+var_D0]
0x1800207e5  mov     rcx, [r13+4C8h]
0x1800207ec  mov     edx, esi
0x1800207ee  mov     rax, [r13+478h]
0x1800207f5  mov     [rsp+120h+var_100], 88h
0x1800207fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020802  cmp     eax, 103h
0x180020807  jnz     short loc_180020851
0x180020809  mov     rcx, [r13+4E0h]
0x180020810  mov     rax, [r13+4A0h]
0x180020817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002081c  test    eax, eax
0x18002081e  jz      short loc_18002085E
0x180020820  jle     short loc_18002082A
0x180020822  movzx   eax, ax
0x180020825  or      eax, 80070000h
0x18002082a  mov     rcx, [rbp+37h+var_40]
0x18002082e  xor     rcx, rsp; StackCookie
0x180020831  call    __security_check_cookie
0x180020836  mov     rbx, [rsp+120h+arg_8]
0x18002083e  add     rsp, 0F0h
0x180020845  pop     r15
0x180020847  pop     r14
0x180020849  pop     r13
0x18002084b  pop     r12
0x18002084d  pop     rdi
0x18002084e  pop     rsi
0x18002084f  pop     rbp
0x180020850  retn
0x180020851  xor     edx, edx
0x180020853  test    eax, eax
0x180020855  jnz     short loc_180020820
0x180020857  cmp     [rsp+120h+var_D0], rbx
0x18002085c  jz      short loc_180020891
0x18002085e  mov     rcx, [r13+4E0h]
0x180020865  lea     rdx, [rsp+120h+var_F0]
0x18002086a  mov     rax, [r13+490h]
0x180020871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020876  test    eax, eax
0x180020878  jnz     short loc_180020820
0x18002087a  mov     rax, [rsp+120h+var_F0]
0x18002087f  cmp     [rsp+120h+var_E8], rax
0x180020884  jnz     loc_1800207BD
0x18002088a  mov     eax, 0D0000225h
0x18002088f  jmp     short loc_18002082A
0x180020891  cmp     [rbp+37h+var_98], dx
0x180020895  jz      loc_180020B74
0x18002089b  mov     rcx, [rbp+37h+lpString1]; lpString1
0x18002089f  test    rcx, rcx
0x1800208a2  jz      loc_180020B74
0x1800208a8  mov     rdx, r15; lpString2
0x1800208ab  call    cs:__imp_lstrcmpiW
0x1800208b1  test    eax, eax
0x1800208b3  jnz     loc_180020B74
0x1800208b9  lea     ebx, [rax+8]
0x1800208bc  test    [rsp+120h+var_C8], bl
0x1800208c0  jnz     short loc_1800208CC
0x1800208c2  mov     eax, 80070490h
0x1800208c7  jmp     loc_18002082A
0x1800208cc  lea     rdx, String2; "Mutant"
0x1800208d3  mov     rcx, r15; lpString1
0x1800208d6  call    cs:__imp_lstrcmpiW
0x1800208dc  xor     ecx, ecx
0x1800208de  test    eax, eax
0x1800208e0  jnz     short loc_180020932
0x1800208e2  test    r14d, r14d
0x1800208e5  jz      short loc_180020911
0x1800208e7  cmp     r14d, esi
0x1800208ea  jnz     loc_180020B05
0x1800208f0  lea     ebx, [rcx+10h]
0x1800208f3  cmp     [rbp+37h+arg_30], ebx
0x1800208f6  jb      loc_180020B23
0x1800208fc  mov     eax, dword ptr [rbp+37h+var_70]
0x1800208ff  lea     esi, [rcx+3]
0x180020902  mov     [rdi], rax
0x180020905  mov     eax, dword ptr [rbp+37h+var_70+4]
0x180020908  mov     [rdi+8], rax
0x18002090c  jmp     loc_180020B3A
0x180020911  cmp     [rbp+37h+arg_30], ebx
0x180020914  jb      loc_180020B23
0x18002091a  xor     eax, eax
0x18002091c  cmp     dword ptr [rbp+37h+var_78+4], ecx
0x18002091f  mov     [rdi], rax
0x180020922  mov     eax, dword ptr [rbp+37h+var_78]
0x180020925  mov     [rdi], eax
0x180020927  setnz   al
0x18002092a  mov     [rdi+5], al
0x18002092d  jmp     loc_180020B3A
0x180020932  lea     rdx, aThread; "Thread"
0x180020939  mov     rcx, r15; lpString1
0x18002093c  call    cs:__imp_lstrcmpiW
0x180020942  xor     esi, esi
0x180020944  test    eax, eax
0x180020946  jnz     short loc_1800209C3
0x180020948  test    r14d, r14d
0x18002094b  jnz     loc_180020B14
0x180020951  cmp     [rbp+37h+arg_30], 30h ; '0'
0x180020955  jb      loc_180020B23
0x18002095b  mov     [rdi+4], esi
0x18002095e  lea     ebx, [rsi+10h]
0x180020961  mov     eax, dword ptr [rbp+37h+var_78]
0x180020964  mov     ecx, [rbp+37h+var_58]
0x180020967  mov     [rdi], eax
0x180020969  mov     rax, [rbp+37h+var_70]
0x18002096d  mov     [rdi+8], rax
0x180020971  mov     eax, dword ptr [rbp+37h+var_68]
0x180020974  mov     [rdi+10h], rax
0x180020978  mov     eax, dword ptr [rbp+37h+var_68+4]
0x18002097b  mov     [rdi+18h], rax
0x18002097f  mov     rax, [rbp+37h+var_60]
0x180020983  mov     [rdi+20h], rax
0x180020987  cmp     ecx, 0FFFFFFF1h
0x18002098a  jz      short loc_180020996
0x18002098c  cmp     ecx, 0Fh
0x18002098f  mov     eax, ebx
0x180020991  cmovnz  eax, ecx
0x180020994  jmp     short loc_18002099B
0x180020996  mov     eax, 0FFFFFFF0h
0x18002099b  mov     [rdi+28h], eax
0x18002099e  mov     eax, [rbp+37h+var_54]
0x1800209a1  cmp     eax, 0FFFFFFF1h
0x1800209a4  jz      short loc_1800209AE
0x1800209a6  cmp     eax, 0Fh
0x1800209a9  cmovnz  ebx, eax
0x1800209ac  jmp     short loc_1800209B3
0x1800209ae  mov     ebx, 0FFFFFFF0h
0x1800209b3  mov     esi, 1
0x1800209b8  mov     [rdi+2Ch], ebx
0x1800209bb  lea     ebx, [rsi+2Fh]
0x1800209be  jmp     loc_180020B3A
0x1800209c3  lea     rdx, aProcess; "Process"
0x1800209ca  mov     rcx, r15; lpString1
0x1800209cd  call    cs:__imp_lstrcmpiW
0x1800209d3  test    eax, eax
0x1800209d5  jnz     short loc_180020A53
0x1800209d7  cmp     r14d, 4
0x1800209db  jnb     loc_180020B05
0x1800209e1  test    r14d, r14d
0x1800209e4  jnz     loc_180020B14
0x1800209ea  lea     ecx, [rax+40h]
0x1800209ed  cmp     [rbp+37h+arg_30], ecx
0x1800209f0  jb      loc_180020B23
0x1800209f6  mov     [rdi+0Ch], esi
0x1800209f9  mov     [rdi+24h], esi
0x1800209fc  mov     [rdi+3Ch], esi
0x1800209ff  mov     eax, dword ptr [rbp+37h+var_78]
0x180020a02  mov     [rdi+8], eax
0x180020a05  mov     rax, [rbp+37h+var_70]
0x180020a09  mov     [rdi+10h], rax
0x180020a0d  mov     rax, [rbp+37h+var_68]
0x180020a11  mov     [rdi+18h], rax
0x180020a15  mov     eax, dword ptr [rbp+37h+var_60]
0x180020a18  mov     [rdi], rcx
0x180020a1b  cmp     eax, 0FFFFFFF1h
0x180020a1e  jz      short loc_180020A2B
0x180020a20  cmp     eax, 0Fh
0x180020a23  lea     ebx, [rcx-30h]
0x180020a26  cmovnz  ebx, eax
0x180020a29  jmp     short loc_180020A30
0x180020a2b  mov     ebx, 0FFFFFFF0h
0x180020a30  mov     eax, dword ptr [rbp+37h+var_60+4]
0x180020a33  mov     esi, 5
0x180020a38  mov     [rdi+28h], rax
0x180020a3c  mov     eax, [rbp+37h+var_58]
0x180020a3f  mov     [rdi+30h], rax
0x180020a43  mov     eax, [rbp+37h+var_54]
0x180020a46  mov     [rdi+20h], ebx
0x180020a49  mov     ebx, ecx
0x180020a4b  mov     [rdi+38h], eax
0x180020a4e  jmp     loc_180020B3A
0x180020a53  lea     rdx, aEvent; "Event"
0x180020a5a  mov     rcx, r15; lpString1
0x180020a5d  call    cs:__imp_lstrcmpiW
0x180020a63  test    eax, eax
0x180020a65  jnz     short loc_180020A9E
0x180020a67  lea     esi, [rax+6]
0x180020a6a  cmp     r14d, esi
0x180020a6d  jnb     loc_180020B05
0x180020a73  xor     ecx, ecx
0x180020a75  test    r14d, r14d
0x180020a78  jnz     loc_180020B14
0x180020a7e  cmp     [rbp+37h+arg_30], ebx
0x180020a81  jb      loc_180020B23
0x180020a87  cmp     dword ptr [rbp+37h+var_78], ecx
0x180020a8a  mov     eax, ecx
0x180020a8c  setz    al
0x180020a8f  cmp     dword ptr [rbp+37h+var_78+4], ecx
0x180020a92  mov     [rdi], eax
0x180020a94  mov     eax, ecx
0x180020a96  setnz   al
0x180020a99  jmp     loc_180020B37
0x180020a9e  lea     rdx, aSection; "Section"
0x180020aa5  mov     rcx, r15; lpString1
0x180020aa8  call    cs:__imp_lstrcmpiW
0x180020aae  test    eax, eax
0x180020ab0  jnz     short loc_180020AE3
0x180020ab2  lea     esi, [rax+7]
0x180020ab5  cmp     r14d, esi
0x180020ab8  jnb     short loc_180020B05
0x180020aba  xor     eax, eax
0x180020abc  test    r14d, r14d
0x180020abf  jnz     short loc_180020B14
0x180020ac1  lea     ebx, [rsi+11h]
0x180020ac4  cmp     [rbp+37h+arg_30], ebx
0x180020ac7  jb      short loc_180020B23
0x180020ac9  mov     [rdi+0Ch], eax
0x180020acc  mov     rax, [rbp+37h+var_78]
0x180020ad0  mov     [rdi], rax
0x180020ad3  mov     eax, dword ptr [rbp+37h+var_70]
0x180020ad6  mov     [rdi+8], eax
0x180020ad9  mov     rax, [rbp+37h+var_68]
0x180020add  mov     [rdi+10h], rax
0x180020ae1  jmp     short loc_180020B3A
0x180020ae3  lea     rdx, aSemaphore; "Semaphore"
0x180020aea  mov     rcx, r15; lpString1
0x180020aed  call    cs:__imp_lstrcmpiW
0x180020af3  test    eax, eax
0x180020af5  jnz     short loc_180020B6A
0x180020af7  lea     esi, [rax+6]
0x180020afa  cmp     [rsp+120h+var_C4], esi
0x180020afe  jnz     short loc_180020B74
0x180020b00  cmp     r14d, ebx
0x180020b03  jb      short loc_180020B0F
0x180020b05  mov     eax, 0D0000003h
0x180020b0a  jmp     loc_18002082A
0x180020b0f  test    r14d, r14d
0x180020b12  jz      short loc_180020B1E
0x180020b14  mov     eax, 1
0x180020b19  jmp     loc_18002082A
0x180020b1e  cmp     [rbp+37h+arg_30], ebx
0x180020b21  jnb     short loc_180020B2D
0x180020b23  mov     eax, 0D0000004h
0x180020b28  jmp     loc_18002082A
0x180020b2d  mov     eax, dword ptr [rbp+37h+var_78]
0x180020b30  mov     esi, ebx
0x180020b32  mov     [rdi], eax
0x180020b34  mov     eax, dword ptr [rbp+37h+var_78+4]
0x180020b37  mov     [rdi+4], eax
0x180020b3a  mov     rax, [rsp+120h+var_D8]
0x180020b3f  mov     [r12], ebx
0x180020b43  mov     [rax], esi
0x180020b45  mov     rdx, [rsp+120h+var_E0]
0x180020b4a  mov     rcx, [r13+4E0h]
0x180020b51  mov     rax, [r13+498h]
0x180020b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b5d  test    eax, eax
0x180020b5f  jnz     loc_180020820
0x180020b65  jmp     loc_18002082A
0x180020b6a  mov     eax, 80070032h
0x180020b6f  jmp     loc_18002082A
0x180020b74  mov     eax, 0D0000024h
0x180020b79  jmp     loc_18002082A
```
