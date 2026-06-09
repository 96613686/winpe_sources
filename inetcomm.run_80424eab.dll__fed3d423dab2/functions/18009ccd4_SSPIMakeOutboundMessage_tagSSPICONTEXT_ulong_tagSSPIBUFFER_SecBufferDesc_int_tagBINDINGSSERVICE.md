# SSPIMakeOutboundMessage(tagSSPICONTEXT *,ulong,tagSSPIBUFFER *,_SecBufferDesc *,int,tagBINDINGSSERVICE)

- ea: `0x18009ccd4`
- end: `0x18009d186`
- name: `?SSPIMakeOutboundMessage@@YAJPEAUtagSSPICONTEXT@@KPEAUtagSSPIBUFFER@@PEAU_SecBufferDesc@@HW4tagBINDINGSSERVICE@@@Z`
- size: `1202`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009c4fc`
- `0x18009d264`

## callees

- `0x18000910c`
- `0x18009bdf8`
- `0x18009c868`
- `0x18009ccd4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18009d005`
- `KERNEL32!WaitForSingleObject` at `0x18009d005`
- `KERNEL32!CompareStringW` at `0x18009ced8`
- `KERNEL32!CompareStringW` at `0x18009cf0a`
- `KERNEL32!CompareStringW` at `0x18009d10f`
- `KERNEL32!CompareStringW` at `0x18009ced8`
- `KERNEL32!CompareStringW` at `0x18009cf0a`
- `KERNEL32!CompareStringW` at `0x18009d10f`
- `KERNEL32!CloseHandle` at `0x18009d00e`
- `KERNEL32!CloseHandle` at `0x18009d00e`
- `KERNEL32!CreateThread` at `0x18009cfe7`
- `KERNEL32!CreateThread` at `0x18009cfe7`

## pseudocode

```c
__int64 __fastcall SSPIMakeOutboundMessage(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6)
{
  __int64 v9; // r15
  int v10; // edi
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r9
  int v13; // r8d
  HANDLE v14; // rax
  void *v15; // rdi
  const unsigned __int16 *v16; // r9
  int v17; // r8d
  int v18; // eax
  __int64 v19; // r8
  struct ITransportCallback *cchCount2; // [rsp+28h] [rbp-D8h]
  struct ITransportCallback *cchCount2a; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  DWORD ThreadId; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v27; // [rsp+88h] [rbp-78h]
  _DWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h]
  int Parameter; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  _DWORD *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v36[1040]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&Parameter, 0, 0x40u);
  v23 = 0;
  v25 = 0;
  ThreadId = 0;
  if ( !a1 || !a3 || !*(_QWORD *)(a1 + 96) || !*(_QWORD *)(a1 + 88) || !*(_QWORD *)(a1 + 136) )
    return 2147942487LL;
  if ( qword_1800F3440 && qword_1800F3448 && *(_BYTE *)(a1 + 32) )
  {
    v9 = 0;
    v26[1] = 1;
    v27 = v28;
    v26[0] = 0;
    v28[0] = 2083;
    v28[1] = 2;
    v29 = a3;
    if ( !a5 && *(_BYTE *)(a1 + 56) )
      v9 = a1 + 64;
    if ( *(_DWORD *)a1 == 2 && a4 )
    {
      v10 = -2146893042;
    }
    else
    {
      memset_0(v36, 0, sizeof(v36));
      if ( a6 )
      {
        if ( a6 == 1 )
        {
          StringCchPrintfW(v36, 0x410u, L"imap/%ls", *(_QWORD *)(a1 + 88));
        }
        else
        {
          v11 = L"smtp/%ls";
          if ( a6 != 2 )
            v11 = L"%ls";
          StringCchPrintfW(v36, 0x410u, v11, *(_QWORD *)(a1 + 88));
        }
      }
      else
      {
        StringCchPrintfW(v36, 0x410u, L"pop/%ls", *(_QWORD *)(a1 + 88));
      }
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, _DWORD, int, __int64, _DWORD, __int64, _DWORD *, int *, __int64 *))(qword_1800F3448 + 48))(
              a1 + 40,
              v9,
              v36,
              0,
              0,
              16,
              a4,
              0,
              a1 + 64,
              v26,
              &v23,
              &v25);
    }
    *(_DWORD *)(a1 + 8) = 2;
    if ( v10 >= 0 )
      goto LABEL_43;
    if ( v10 != -2146893042 )
      return (unsigned int)v10;
    if ( *(_DWORD *)(a1 + 128) == 1
      && (CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 96), -1, L"MSN", -1) == 2 && !*(_DWORD *)(a1 + 12)
       || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 96), -1, L"NTLM", -1) == 2 && *(_DWORD *)(a1 + 12) == 1) )
    {
      v12 = *(const unsigned __int16 **)(a1 + 96);
      v13 = *(_DWORD *)(a1 + 80);
      cchCount2 = *(struct ITransportCallback **)(a1 + 136);
      *(_DWORD *)a1 = 1;
      if ( (int)SSPILogon((struct tagSSPICONTEXT *)a1, 0, v13, v12, 0, cchCount2) >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, int, _QWORD, _DWORD, __int64, _DWORD *, int *, __int64 *))(qword_1800F3448 + 48))(
                a1 + 40,
                0,
                *(_QWORD *)(a1 + 88),
                0,
                0,
                16,
                0,
                0,
                a1 + 64,
                v26,
                &v23,
                &v25);
        if ( v10 >= 0 )
          goto LABEL_43;
      }
    }
    v31 = a1;
    v33 = v26;
    v32 = a4;
    v34 = v9;
    v35 = 0;
    v14 = CreateThread(0, 0, SSPIPromptThreadEntry, &Parameter, 0, &ThreadId);
    v15 = v14;
    if ( !v14 )
      return (unsigned int)-2147024882;
    WaitForSingleObject(v14, 0xFFFFFFFF);
    CloseHandle(v15);
    v10 = Parameter;
    if ( Parameter >= 0 )
      goto LABEL_43;
    if ( Parameter == -2146893042 )
      return (unsigned int)v10;
    if ( a4 )
      goto LABEL_42;
    v16 = *(const unsigned __int16 **)(a1 + 96);
    v17 = *(_DWORD *)(a1 + 80);
    cchCount2a = *(struct ITransportCallback **)(a1 + 136);
    *(_DWORD *)a1 = 3;
    v18 = SSPILogon((struct tagSSPICONTEXT *)a1, 1, v17, v16, 0, cchCount2a);
    v10 = v18;
    if ( *(_BYTE *)(a1 + 16) )
      return (unsigned int)-2147467259;
    if ( v18 >= 0 )
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, int, _QWORD, _DWORD, __int64, _DWORD *, int *, __int64 *))(qword_1800F3448 + 48))(
              a1 + 40,
              v9,
              *(_QWORD *)(a1 + 88),
              0,
              0,
              16,
              0,
              0,
              a1 + 64,
              v26,
              &v23,
              &v25);
    if ( v10 >= 0 )
    {
LABEL_43:
      *(_BYTE *)(a1 + 56) = 1;
      if ( *(_DWORD *)(a1 + 128) == 1 )
        CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a1 + 96), -1, L"MSN", -1);
    }
    else
    {
LABEL_42:
      v10 = 0;
      v28[0] = 0;
    }
    v19 = v28[0];
    *(_DWORD *)(a3 + 2088) = v10 == 590610;
    *(_DWORD *)(a3 + 2084) = v19 + 1;
    *(_BYTE *)(v19 + a3) = 0;
    v10 = SSPIEncodeBuffer(*(_DWORD *)(a1 + 80), (struct tagSSPIBUFFER *)a3);
    if ( v10 >= 0 )
      return 0;
    return (unsigned int)v10;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18009ccd4  mov     [rsp-8+arg_8], rbx
0x18009ccd9  push    rbp
0x18009ccda  push    rsi
0x18009ccdb  push    rdi
0x18009ccdc  push    r12
0x18009ccde  push    r13
0x18009cce0  push    r14
0x18009cce2  push    r15
0x18009cce4  lea     rbp, [rsp-810h]
0x18009ccec  sub     rsp, 910h
0x18009ccf3  mov     rax, cs:__security_cookie
0x18009ccfa  xor     rax, rsp
0x18009ccfd  mov     [rbp+840h+var_40], rax
0x18009cd04  xor     edx, edx; Val
0x18009cd06  mov     rsi, r8
0x18009cd09  mov     rbx, rcx
0x18009cd0c  mov     r14, r9
0x18009cd0f  lea     rcx, [rbp+840h+Parameter]; void *
0x18009cd13  lea     r8d, [rdx+40h]; Size
0x18009cd17  call    memset_0
0x18009cd1c  xor     r12d, r12d
0x18009cd1f  mov     [rsp+940h+var_8D0], r12d
0x18009cd24  mov     [rsp+940h+var_8C8], r12
0x18009cd29  mov     [rsp+940h+ThreadId], r12d
0x18009cd2e  test    rbx, rbx
0x18009cd31  jz      loc_18009D157
0x18009cd37  test    rsi, rsi
0x18009cd3a  jz      loc_18009D157
0x18009cd40  cmp     [rbx+60h], r12
0x18009cd44  jz      loc_18009D157
0x18009cd4a  cmp     [rbx+58h], r12
0x18009cd4e  jz      loc_18009D157
0x18009cd54  cmp     [rbx+88h], r12
0x18009cd5b  jz      loc_18009D157
0x18009cd61  cmp     cs:qword_1800F3440, r12
0x18009cd68  jz      loc_18009D150
0x18009cd6e  cmp     cs:qword_1800F3448, r12
0x18009cd75  jz      loc_18009D150
0x18009cd7b  cmp     [rbx+20h], r12b
0x18009cd7f  jz      loc_18009D150
0x18009cd85  lea     r13d, [r12+1]
0x18009cd8a  mov     r15d, r12d
0x18009cd8d  lea     rax, [rbp+840h+var_8B0]
0x18009cd91  mov     [rbp+840h+var_8BC], r13d
0x18009cd95  mov     [rbp+840h+var_8B8], rax
0x18009cd99  mov     [rbp+840h+var_8C0], r12d
0x18009cd9d  mov     [rbp+840h+var_8B0], 823h
0x18009cda4  mov     [rbp+840h+var_8AC], 2
0x18009cdab  mov     [rbp+840h+var_8A8], rsi
0x18009cdaf  cmp     [rbp+840h+arg_20], r12d
0x18009cdb6  jnz     short loc_18009CDC2
0x18009cdb8  cmp     [rbx+38h], r12b
0x18009cdbc  jz      short loc_18009CDC2
0x18009cdbe  lea     r15, [rbx+40h]
0x18009cdc2  cmp     dword ptr [rbx], 2
0x18009cdc5  jnz     short loc_18009CDD6
0x18009cdc7  test    r14, r14
0x18009cdca  jz      short loc_18009CDD6
0x18009cdcc  mov     edi, 8009030Eh
0x18009cdd1  jmp     loc_18009CE8C
0x18009cdd6  xor     edx, edx; Val
0x18009cdd8  lea     rcx, [rbp+840h+var_860]; void *
0x18009cddc  mov     r8d, 820h; Size
0x18009cde2  call    memset_0
0x18009cde7  mov     eax, [rbp+840h+arg_28]
0x18009cded  test    eax, eax
0x18009cdef  jnz     short loc_18009CDFA
0x18009cdf1  lea     r8, aPopLs; "pop/%ls"
0x18009cdf8  jmp     short loc_18009CE1D
0x18009cdfa  cmp     eax, r13d
0x18009cdfd  jnz     short loc_18009CE08
0x18009cdff  lea     r8, aImapLs; "imap/%ls"
0x18009ce06  jmp     short loc_18009CE1D
0x18009ce08  cmp     eax, 2
0x18009ce0b  lea     r8, aSmtpLs; "smtp/%ls"
0x18009ce12  lea     rcx, aLs; "%ls"
0x18009ce19  cmovnz  r8, rcx; unsigned __int16 *
0x18009ce1d  mov     r9, [rbx+58h]
0x18009ce21  lea     rcx, [rbp+840h+var_860]; unsigned __int16 *
0x18009ce25  mov     edx, 410h; unsigned __int64
0x18009ce2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009ce2f  mov     rax, cs:qword_1800F3448
0x18009ce36  lea     r8, [rsp+940h+var_8C8]
0x18009ce3b  mov     [rsp+940h+var_8E8], r8
0x18009ce40  lea     rdx, [rbx+40h]
0x18009ce44  lea     r8, [rsp+940h+var_8D0]
0x18009ce49  xor     r9d, r9d
0x18009ce4c  mov     [rsp+940h+var_8F0], r8
0x18009ce51  lea     rcx, [rbx+28h]
0x18009ce55  mov     rax, [rax+30h]
0x18009ce59  lea     r8, [rbp+840h+var_8C0]
0x18009ce5d  mov     [rsp+940h+var_8F8], r8
0x18009ce62  lea     r8, [rbp+840h+var_860]
0x18009ce66  mov     [rsp+940h+var_900], rdx
0x18009ce6b  mov     rdx, r15
0x18009ce6e  mov     [rsp+940h+var_908], r12d
0x18009ce73  mov     [rsp+940h+var_910], r14
0x18009ce78  mov     [rsp+940h+cchCount2], 10h
0x18009ce80  mov     dword ptr [rsp+940h+lpString2], r12d
0x18009ce85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce8a  mov     edi, eax
0x18009ce8c  mov     dword ptr [rbx+8], 2
0x18009ce93  lea     rax, aMsn; "MSN"
0x18009ce9a  test    edi, edi
0x18009ce9c  jns     loc_18009D0E5
0x18009cea2  cmp     edi, 8009030Eh
0x18009cea8  jnz     loc_18009D14C
0x18009ceae  cmp     [rbx+80h], r13d
0x18009ceb5  jnz     loc_18009CFB1
0x18009cebb  mov     r8, [rbx+60h]; lpString1
0x18009cebf  or      r9d, 0FFFFFFFFh; cchCount1
0x18009cec3  mov     [rsp+940h+cchCount2], 0FFFFFFFFh; cchCount2
0x18009cecb  mov     edx, r13d; dwCmpFlags
0x18009cece  mov     ecx, 7Fh; Locale
0x18009ced3  mov     [rsp+940h+lpString2], rax; lpString2
0x18009ced8  call    cs:__imp_CompareStringW
0x18009cede  cmp     eax, 2
0x18009cee1  jnz     short loc_18009CEE9
0x18009cee3  cmp     [rbx+0Ch], r12d
0x18009cee7  jz      short loc_18009CF23
0x18009cee9  mov     r8, [rbx+60h]; lpString1
0x18009ceed  lea     rax, aNtlm; "NTLM"
0x18009cef4  or      r9d, 0FFFFFFFFh; cchCount1
0x18009cef8  mov     edx, r13d; dwCmpFlags
0x18009cefb  mov     [rsp+940h+cchCount2], r9d; cchCount2
0x18009cf00  mov     ecx, 7Fh; Locale
0x18009cf05  mov     [rsp+940h+lpString2], rax; lpString2
0x18009cf0a  call    cs:__imp_CompareStringW
0x18009cf10  cmp     eax, 2
0x18009cf13  jnz     loc_18009CFB1
0x18009cf19  cmp     [rbx+0Ch], r13d
0x18009cf1d  jnz     loc_18009CFB1
0x18009cf23  mov     rax, [rbx+88h]
0x18009cf2a  xor     edx, edx; int
0x18009cf2c  mov     r9, [rbx+60h]; unsigned __int16 *
0x18009cf30  mov     rcx, rbx; struct tagSSPICONTEXT *
0x18009cf33  mov     r8d, [rbx+50h]; int
0x18009cf37  mov     qword ptr [rsp+940h+cchCount2], rax; struct ITransportCallback *
0x18009cf3c  mov     [rsp+940h+lpString2], r12; struct INETSERVERW *
0x18009cf41  mov     [rbx], r13d
0x18009cf44  call    ?SSPILogon@@YAJPEAUtagSSPICONTEXT@@HHPEBGPEAUINETSERVERW@@PEAUITransportCallback@@@Z; SSPILogon(tagSSPICONTEXT *,int,int,ushort const *,INETSERVERW *,ITransportCallback *)
0x18009cf49  test    eax, eax
0x18009cf4b  js      short loc_18009CFB1
0x18009cf4d  mov     rax, cs:qword_1800F3448
0x18009cf54  lea     r8, [rsp+940h+var_8C8]
0x18009cf59  mov     [rsp+940h+var_8E8], r8
0x18009cf5e  lea     rdx, [rbx+40h]
0x18009cf62  lea     r8, [rsp+940h+var_8D0]
0x18009cf67  xor     r9d, r9d
0x18009cf6a  mov     [rsp+940h+var_8F0], r8
0x18009cf6f  lea     rcx, [rbx+28h]
0x18009cf73  mov     rax, [rax+30h]
0x18009cf77  lea     r8, [rbp+840h+var_8C0]
0x18009cf7b  mov     [rsp+940h+var_8F8], r8
0x18009cf80  mov     r8, [rbx+58h]
0x18009cf84  mov     [rsp+940h+var_900], rdx
0x18009cf89  xor     edx, edx
0x18009cf8b  mov     [rsp+940h+var_908], r12d
0x18009cf90  mov     [rsp+940h+var_910], r12
0x18009cf95  mov     [rsp+940h+cchCount2], 10h
0x18009cf9d  mov     dword ptr [rsp+940h+lpString2], r12d
0x18009cfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cfa7  mov     edi, eax
0x18009cfa9  test    eax, eax
0x18009cfab  jns     loc_18009D0DE
0x18009cfb1  lea     rax, [rbp+840h+var_8C0]
0x18009cfb5  mov     [rbp+840h+var_898], rbx
0x18009cfb9  mov     [rbp+840h+var_880], rax
0x18009cfbd  lea     r9, [rbp+840h+Parameter]; lpParameter
0x18009cfc1  lea     rax, [rsp+940h+ThreadId]
0x18009cfc6  mov     [rbp+840h+var_888], r14
0x18009cfca  mov     qword ptr [rsp+940h+cchCount2], rax; lpThreadId
0x18009cfcf  lea     r8, ?SSPIPromptThreadEntry@@YAKPEAK@Z; lpStartAddress
0x18009cfd6  xor     edx, edx; dwStackSize
0x18009cfd8  mov     dword ptr [rsp+940h+lpString2], r12d; dwCreationFlags
0x18009cfdd  xor     ecx, ecx; lpThreadAttributes
0x18009cfdf  mov     [rbp+840h+var_870], r15
0x18009cfe3  mov     [rbp+840h+var_868], r12d
0x18009cfe7  call    cs:__imp_CreateThread
0x18009cfed  mov     rdi, rax
0x18009cff0  test    rax, rax
0x18009cff3  jnz     short loc_18009CFFF
0x18009cff5  mov     edi, 8007000Eh
0x18009cffa  jmp     loc_18009D14C
0x18009cfff  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009d002  mov     rcx, rdi; hHandle
0x18009d005  call    cs:__imp_WaitForSingleObject
0x18009d00b  mov     rcx, rdi; hObject
0x18009d00e  call    cs:__imp_CloseHandle
0x18009d014  mov     edi, [rbp+840h+Parameter]
0x18009d017  test    edi, edi
0x18009d019  jns     loc_18009D0DE
0x18009d01f  cmp     edi, 8009030Eh
0x18009d025  jz      loc_18009D14C
0x18009d02b  test    r14, r14
0x18009d02e  jnz     loc_18009D0D5
0x18009d034  mov     rax, [rbx+88h]
0x18009d03b  mov     edx, r13d; int
0x18009d03e  mov     r9, [rbx+60h]; unsigned __int16 *
0x18009d042  mov     rcx, rbx; struct tagSSPICONTEXT *
0x18009d045  mov     r8d, [rbx+50h]; int
0x18009d049  mov     qword ptr [rsp+940h+cchCount2], rax; struct ITransportCallback *
0x18009d04e  mov     [rsp+940h+lpString2], r12; struct INETSERVERW *
0x18009d053  mov     dword ptr [rbx], 3
0x18009d059  call    ?SSPILogon@@YAJPEAUtagSSPICONTEXT@@HHPEBGPEAUINETSERVERW@@PEAUITransportCallback@@@Z; SSPILogon(tagSSPICONTEXT *,int,int,ushort const *,INETSERVERW *,ITransportCallback *)
0x18009d05e  mov     edi, eax
0x18009d060  cmp     [rbx+10h], r12b
0x18009d064  jz      short loc_18009D070
0x18009d066  mov     edi, 80004005h
0x18009d06b  jmp     loc_18009D14C
0x18009d070  test    eax, eax
0x18009d072  js      short loc_18009D0D1
0x18009d074  mov     rax, cs:qword_1800F3448
0x18009d07b  lea     r8, [rsp+940h+var_8C8]
0x18009d080  mov     [rsp+940h+var_8E8], r8
0x18009d085  lea     rdx, [rbx+40h]
0x18009d089  lea     r8, [rsp+940h+var_8D0]
0x18009d08e  xor     r9d, r9d
0x18009d091  mov     [rsp+940h+var_8F0], r8
0x18009d096  lea     rcx, [rbx+28h]
0x18009d09a  mov     rax, [rax+30h]
0x18009d09e  lea     r8, [rbp+840h+var_8C0]
0x18009d0a2  mov     [rsp+940h+var_8F8], r8
0x18009d0a7  mov     r8, [rbx+58h]
0x18009d0ab  mov     [rsp+940h+var_900], rdx
0x18009d0b0  mov     rdx, r15
0x18009d0b3  mov     [rsp+940h+var_908], r12d
0x18009d0b8  mov     [rsp+940h+var_910], r12
0x18009d0bd  mov     [rsp+940h+cchCount2], 10h
0x18009d0c5  mov     dword ptr [rsp+940h+lpString2], r12d
0x18009d0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0cf  mov     edi, eax
0x18009d0d1  test    edi, edi
0x18009d0d3  jns     short loc_18009D0DE
0x18009d0d5  mov     edi, r12d
0x18009d0d8  mov     [rbp+840h+var_8B0], r12d
0x18009d0dc  jmp     short loc_18009D115
0x18009d0de  lea     rax, aMsn; "MSN"
0x18009d0e5  mov     [rbx+38h], r13b
0x18009d0e9  cmp     [rbx+80h], r13d
0x18009d0f0  jnz     short loc_18009D115
0x18009d0f2  mov     r8, [rbx+60h]; lpString1
0x18009d0f6  or      r9d, 0FFFFFFFFh; cchCount1
0x18009d0fa  mov     [rsp+940h+cchCount2], 0FFFFFFFFh; cchCount2
0x18009d102  mov     edx, r13d; dwCmpFlags
0x18009d105  mov     ecx, 7Fh; Locale
0x18009d10a  mov     [rsp+940h+lpString2], rax; lpString2
0x18009d10f  call    cs:__imp_CompareStringW
0x18009d115  mov     r8d, [rbp+840h+var_8B0]
0x18009d119  mov     eax, r12d
0x18009d11c  cmp     edi, 90312h
0x18009d122  mov     rdx, rsi; struct tagSSPIBUFFER *
0x18009d125  setz    al
0x18009d128  mov     [rsi+828h], eax
0x18009d12e  lea     eax, [r8+1]
0x18009d132  mov     [rsi+824h], eax
0x18009d138  mov     [r8+rsi], r12b
0x18009d13c  mov     ecx, [rbx+50h]; int
0x18009d13f  call    ?SSPIEncodeBuffer@@YAJHPEAUtagSSPIBUFFER@@@Z; SSPIEncodeBuffer(int,tagSSPIBUFFER *)
0x18009d144  test    eax, eax
0x18009d146  mov     edi, eax
0x18009d148  cmovns  edi, r12d
0x18009d14c  mov     eax, edi
0x18009d14e  jmp     short loc_18009D15C
0x18009d150  mov     eax, 8000FFFFh
0x18009d155  jmp     short loc_18009D15C
0x18009d157  mov     eax, 80070057h
0x18009d15c  mov     rcx, [rbp+840h+var_40]
0x18009d163  xor     rcx, rsp; StackCookie
0x18009d166  call    __security_check_cookie
0x18009d16b  mov     rbx, [rsp+940h+arg_8]
0x18009d173  add     rsp, 910h
0x18009d17a  pop     r15
0x18009d17c  pop     r14
0x18009d17e  pop     r13
0x18009d180  pop     r12
0x18009d182  pop     rdi
0x18009d183  pop     rsi
0x18009d184  pop     rbp
0x18009d185  retn
```
