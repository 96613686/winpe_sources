# LdrpLoadForwardedDll

- ea: `0x180022aa0`
- end: `0x180022fad`
- name: `LdrpLoadForwardedDll`
- size: `1293`
- prototype: `__int64 __usercall@<rax>(PCANSI_STRING SourceString@<rcx>, int, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180053390`
- `0x1800bc71c`

## callees

- `0x1800195a0`
- `0x18001a0d0`
- `0x18001d490`
- `0x18001dc60`
- `0x180021c80`
- `0x180021fe0`
- `0x180022170`
- `0x180022aa0`
- `0x1800249a0`
- `0x18011fba4`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall LdrpLoadForwardedDll(
        PCANSI_STRING SourceString,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 *a6)
{
  __int64 *v10; // r15
  int v11; // ebx
  int Length; // eax
  char *Buffer; // r9
  int v14; // edx
  unsigned __int16 v15; // cx
  __int64 v16; // r8
  unsigned int v17; // edi
  __int64 v18; // rdi
  _ACTIVATION_CONTEXT_STACK *ActivationContextStackPointer; // rsi
  unsigned __int64 ActiveFrame; // rbx
  __int64 v22; // rcx
  void *v23; // r15
  void *Atom; // rax
  signed __int32 v25[8]; // [rsp+0h] [rbp-3C8h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-378h] BYREF
  int v27[3]; // [rsp+54h] [rbp-374h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-368h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp-358h] BYREF
  __int128 v30; // [rsp+80h] [rbp-348h] BYREF
  __int128 v31; // [rsp+90h] [rbp-338h]
  __int128 v32; // [rsp+A0h] [rbp-328h]
  __int64 v33; // [rsp+B0h] [rbp-318h]
  EXCEPTION_RECORD ExceptionRecord; // [rsp+C0h] [rbp-308h] BYREF
  _DWORD v35[2]; // [rsp+160h] [rbp-268h] BYREF
  void *Src; // [rsp+168h] [rbp-260h]
  __int16 v37; // [rsp+170h] [rbp-258h] BYREF
  _BYTE v38[254]; // [rsp+172h] [rbp-256h] BYREF
  char ArgList[4]; // [rsp+270h] [rbp-158h] BYREF
  int v40; // [rsp+274h] [rbp-154h]
  __int16 *v41; // [rsp+278h] [rbp-150h]
  __int16 v42; // [rsp+280h] [rbp-148h] BYREF
  _BYTE v43[254]; // [rsp+282h] [rbp-146h] BYREF
  _UNKNOWN *retaddr; // [rsp+3C8h] [rbp+0h]

  v10 = a6;
  *(_QWORD *)&v27[1] = a6;
  v40 = 0;
  memset_thunk_772440563353939046(v43, 0, 0xFEu);
  v27[0] = 0;
  v35[1] = 0;
  memset_thunk_772440563353939046(v38, 0, 0xFEu);
  v41 = &v42;
  *(_DWORD *)ArgList = 0x1000000;
  v42 = 0;
  Src = &v37;
  v35[0] = 0x1000000;
  v37 = 0;
  DestinationString = 0;
  v11 = 0;
  Length = SourceString->Length;
  if ( !(_WORD)Length )
    goto LABEL_9;
  v26 = 0;
  Buffer = SourceString->Buffer;
  _InterlockedOr(v25, 0);
  if ( word_1801C4FD0 == -535 || GlobalRtlNlsState == -535 )
  {
    RtlUTF8ToUnicodeN(0, 0, (unsigned int)&v26, (_DWORD)Buffer, Length);
    v14 = v26;
  }
  else
  {
    _InterlockedOr(v25, 0);
    v14 = 0;
    if ( word_1801C4F9C )
    {
      while ( Length )
      {
        --Length;
        v22 = (unsigned __int8)*Buffer++;
        if ( *(_WORD *)(qword_1801C5020 + 2 * v22) )
        {
          if ( !Length )
          {
            v14 += 2;
            break;
          }
          --Length;
          ++Buffer;
        }
        v14 += 2;
      }
    }
    else
    {
      v14 = 2 * Length;
    }
  }
  v15 = v35[0];
  v16 = v14 + (unsigned int)LOWORD(v35[0]) + 2;
  LOWORD(v17) = HIWORD(v35[0]);
  if ( (unsigned int)v16 > HIWORD(v35[0]) )
  {
    if ( (unsigned int)v16 > 0xFFFE )
    {
      v11 = -1073741562;
      goto LABEL_7;
    }
    v17 = (v16 + 63) & 0xFFFFFFC0;
    if ( v17 > 0xFFFE )
      v17 = 65534;
    if ( Src == &v37 )
    {
      Atom = (void *)RtlpAllocateAtom(v17);
      v23 = Atom;
      if ( Atom )
      {
        v15 = v35[0];
        if ( !LOWORD(v35[0]) )
          goto LABEL_42;
        memmove(Atom, Src, LOWORD(v35[0]));
      }
    }
    else
    {
      v23 = (void *)NtdllpReallocateStringRoutine(v17, Src, v16, Buffer);
    }
    v15 = v35[0];
LABEL_42:
    if ( v23 )
    {
      Src = v23;
      HIWORD(v35[0]) = v17;
    }
    else
    {
      v11 = -1073741801;
      LOWORD(v17) = HIWORD(v35[0]);
    }
    v10 = *(__int64 **)&v27[1];
  }
LABEL_7:
  if ( v11 >= 0 )
  {
    DestinationString.Buffer = (wchar_t *)((char *)Src + v15);
    DestinationString.Length = 0;
    DestinationString.MaximumLength = v17 - v15;
    RtlAnsiStringToUnicodeString(&DestinationString, SourceString, 0);
    LOWORD(v35[0]) += DestinationString.Length;
  }
LABEL_9:
  v27[0] = v11;
  if ( v11 < 0 )
    goto LABEL_21;
  v29[0] = 72;
  v29[1] = 1;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v18 = *(_QWORD *)(a4 + 136);
  ActivationContextStackPointer = NtCurrentTeb()->ActivationContextStackPointer;
  if ( ActivationContextStackPointer )
    ActiveFrame = (unsigned __int64)ActivationContextStackPointer->ActiveFrame;
  else
    ActiveFrame = 0;
  memset_thunk_772440563353939046(&ExceptionRecord, 0, 0x98u);
  if ( v29[0] >= 0x48u )
  {
    *((_QWORD *)&v31 + 1) = ~ActiveFrame;
    *(_QWORD *)&v32 = ~v18;
    *((_QWORD *)&v32 + 1) = retaddr;
  }
  if ( ActiveFrame && (*(_DWORD *)(ActiveFrame + 16) & 0x70) != 0x20 )
  {
    ExceptionRecord.NumberParameters = 4;
    ExceptionRecord.ExceptionInformation[0] = (unsigned __int64)ActivationContextStackPointer;
    ExceptionRecord.ExceptionInformation[1] = ActiveFrame;
    ExceptionRecord.ExceptionInformation[2] = ActiveFrame;
    ExceptionRecord.ExceptionInformation[3] = *(unsigned int *)(ActiveFrame + 16);
    ExceptionRecord.ExceptionCode = -1072365548;
    ExceptionRecord.ExceptionFlags = 1;
    RtlRaiseException(&ExceptionRecord);
    goto LABEL_18;
  }
  *(_QWORD *)&v30 = ActiveFrame;
  *((_QWORD *)&v30 + 1) = v18;
  LODWORD(v31) = 32;
  if ( ActiveFrame )
  {
    if ( *(_QWORD *)(ActiveFrame + 8) == v18 )
      goto LABEL_17;
LABEL_33:
    ActivationContextStackPointer->ActiveFrame = (_RTL_ACTIVATION_CONTEXT_STACK_FRAME *)&v30;
    goto LABEL_18;
  }
  if ( v18 )
    goto LABEL_33;
LABEL_17:
  LODWORD(v31) = 48;
LABEL_18:
  v26 = 0;
  v27[0] = LdrpPreprocessDllName((unsigned __int16 *)v35, (unsigned __int16 *)ArgList, a4, &v26);
  if ( v27[0] >= 0 )
    LdrpLoadDllInternal((__int64)ArgList, a2, v26, a5, a4, a3, v10, v27, 0, 0);
  RtlDeactivateActivationContextUnsafeFast(v29);
LABEL_21:
  if ( &v37 != Src )
    RtlpSysVolFree(Src);
  Src = &v37;
  v35[0] = 0x1000000;
  v37 = 0;
  if ( &v42 != v41 )
    RtlpSysVolFree(v41);
  return (unsigned int)v27[0];
}

```

## disassembly

```asm
0x180022aa0  push    rbx
0x180022aa2  push    rsi
0x180022aa3  push    rdi
0x180022aa4  push    r12
0x180022aa6  push    r13
0x180022aa8  push    r14
0x180022aaa  push    r15
0x180022aac  sub     rsp, 390h
0x180022ab3  mov     rax, cs:__security_cookie
0x180022aba  xor     rax, rsp
0x180022abd  mov     [rsp+3C8h+var_48], rax
0x180022ac5  mov     r14, r9
0x180022ac8  mov     r13, r8
0x180022acb  mov     r12, rdx
0x180022ace  mov     rsi, rcx
0x180022ad1  mov     r15, [rsp+3C8h+arg_28]
0x180022ad9  mov     qword ptr [rsp+3C8h+var_374+4], r15
0x180022ade  xor     eax, eax
0x180022ae0  mov     [rsp+3C8h+var_154], eax
0x180022ae7  xor     edx, edx; Val
0x180022ae9  mov     r8d, 0FEh; Size
0x180022aef  lea     rcx, [rsp+3C8h+var_146]; void *
0x180022af7  call    memset$thunk$772440563353939046
0x180022afc  xor     edi, edi
0x180022afe  mov     dword ptr [rsp+3C8h+var_374], edi
0x180022b02  xor     eax, eax
0x180022b04  mov     [rsp+3C8h+var_264], eax
0x180022b0b  xor     edx, edx; Val
0x180022b0d  mov     r8d, 0FEh; Size
0x180022b13  lea     rcx, [rsp+3C8h+var_256]; void *
0x180022b1b  call    memset$thunk$772440563353939046
0x180022b20  lea     rax, [rsp+3C8h+var_148]
0x180022b28  mov     [rsp+3C8h+var_150], rax
0x180022b30  mov     dword ptr [rsp+3C8h+ArgList], 1000000h
0x180022b3b  mov     [rsp+3C8h+var_148], di
0x180022b43  lea     rax, [rsp+3C8h+var_258]
0x180022b4b  mov     [rsp+3C8h+Src], rax
0x180022b53  mov     [rsp+3C8h+var_268], 1000000h
0x180022b5e  mov     [rsp+3C8h+var_258], di
0x180022b66  xorps   xmm0, xmm0
0x180022b69  movups  xmmword ptr [rsp+3C8h+DestinationString.Length], xmm0
0x180022b6e  mov     ebx, edi
0x180022b70  movzx   eax, word ptr [rsi]
0x180022b73  test    ax, ax
0x180022b76  jz      loc_180022C2B
0x180022b7c  mov     [rsp+3C8h+var_378], edi
0x180022b80  mov     r9, [rsi+8]
0x180022b84  lock or [rsp+3C8h+var_3C8], ebx
0x180022b88  mov     ecx, 0FDE9h
0x180022b8d  cmp     cs:word_1801C4FD0, cx
0x180022b94  jz      loc_180022E10
0x180022b9a  cmp     cs:GlobalRtlNlsState, cx
0x180022ba1  jz      loc_180022E10
0x180022ba7  lock or [rsp+3C8h+var_3C8], ebx
0x180022bab  mov     edx, edi
0x180022bad  cmp     cs:word_1801C4F9C, di
0x180022bb4  setnz   cl
0x180022bb7  mov     r8, cs:qword_1801C5020
0x180022bbe  test    cl, cl
0x180022bc0  jnz     loc_180022E30
0x180022bc6  lea     edx, [rax+rax]
0x180022bc9  movzx   ecx, word ptr [rsp+3C8h+var_268]
0x180022bd1  lea     r8d, [rcx+2]
0x180022bd5  add     r8d, edx
0x180022bd8  movzx   edi, word ptr [rsp+3C8h+var_268+2]
0x180022be0  cmp     r8d, edi
0x180022be3  ja      loc_180022EE0
0x180022be9  test    ebx, ebx
0x180022beb  js      short loc_180022C29
0x180022bed  movzx   eax, cx
0x180022bf0  add     rax, [rsp+3C8h+Src]
0x180022bf8  mov     [rsp+3C8h+DestinationString.Buffer], rax
0x180022bfd  xor     eax, eax
0x180022bff  mov     [rsp+3C8h+DestinationString.Length], ax
0x180022c04  sub     di, cx
0x180022c07  mov     [rsp+3C8h+DestinationString.MaximumLength], di
0x180022c0c  xor     r8d, r8d; AllocateDestinationString
0x180022c0f  mov     rdx, rsi; SourceString
0x180022c12  lea     rcx, [rsp+3C8h+DestinationString]; DestinationString
0x180022c17  call    RtlAnsiStringToUnicodeString
0x180022c1c  movzx   eax, [rsp+3C8h+DestinationString.Length]
0x180022c21  add     word ptr [rsp+3C8h+var_268], ax
0x180022c29  xor     edi, edi
0x180022c2b  mov     dword ptr [rsp+3C8h+var_374], ebx
0x180022c2f  test    ebx, ebx
0x180022c31  js      loc_180022D91
0x180022c37  mov     [rsp+3C8h+var_358], 48h ; 'H'
0x180022c40  mov     [rsp+3C8h+var_350], 1
0x180022c49  xorps   xmm0, xmm0
0x180022c4c  xor     eax, eax
0x180022c4e  movups  [rsp+3C8h+var_348], xmm0
0x180022c56  movups  [rsp+3C8h+var_338], xmm0
0x180022c5e  movups  [rsp+3C8h+var_328], xmm0
0x180022c66  mov     [rsp+3C8h+var_318], rax
0x180022c6e  mov     rdi, [r14+88h]
0x180022c75  mov     rax, gs:30h
0x180022c7e  mov     rsi, [rax+2C8h]
0x180022c85  test    rsi, rsi
0x180022c88  jz      loc_180022F98
0x180022c8e  mov     rbx, [rsi]
0x180022c91  xor     edx, edx; Val
0x180022c93  mov     r8d, 98h; Size
0x180022c99  lea     rcx, [rsp+3C8h+ExceptionRecord]; void *
0x180022ca1  call    memset$thunk$772440563353939046
0x180022ca6  cmp     [rsp+3C8h+var_358], 48h ; 'H'
0x180022cac  jb      short loc_180022CDA
0x180022cae  mov     rax, rbx
0x180022cb1  not     rax
0x180022cb4  mov     qword ptr [rsp+3C8h+var_338+8], rax
0x180022cbc  mov     rax, rdi
0x180022cbf  not     rax
0x180022cc2  mov     qword ptr [rsp+3C8h+var_328], rax
0x180022cca  mov     rax, [rsp+3C8h]
0x180022cd2  mov     qword ptr [rsp+3C8h+var_328+8], rax
0x180022cda  test    rbx, rbx
0x180022cdd  jnz     loc_180022E51
0x180022ce3  mov     qword ptr [rsp+3C8h+var_348], rbx
0x180022ceb  mov     qword ptr [rsp+3C8h+var_348+8], rdi
0x180022cf3  mov     dword ptr [rsp+3C8h+var_338], 20h ; ' '
0x180022cfe  test    rbx, rbx
0x180022d01  jnz     loc_180022EB4
0x180022d07  test    rdi, rdi
0x180022d0a  jnz     loc_180022F9F
0x180022d10  mov     dword ptr [rsp+3C8h+var_338], 30h ; '0'
0x180022d1b  xor     edi, edi
0x180022d1d  mov     [rsp+3C8h+var_378], edi
0x180022d21  lea     r9, [rsp+3C8h+var_378]
0x180022d26  mov     r8, r14
0x180022d29  lea     rdx, [rsp+3C8h+ArgList]
0x180022d31  lea     rcx, [rsp+3C8h+var_268]
0x180022d39  call    LdrpPreprocessDllName
0x180022d3e  mov     dword ptr [rsp+3C8h+var_374], eax
0x180022d42  test    eax, eax
0x180022d44  js      short loc_180022D87
0x180022d46  mov     qword ptr [rsp+3C8h+var_380], rdi; char
0x180022d4b  mov     [rsp+3C8h+var_388], rdi; __int64
0x180022d50  lea     rax, [rsp+3C8h+var_374]
0x180022d55  mov     [rsp+3C8h+var_390], rax; __int64
0x180022d5a  mov     [rsp+3C8h+var_398], r15; __int64
0x180022d5f  mov     [rsp+3C8h+var_3A0], r13; __int64
0x180022d64  mov     [rsp+3C8h+var_3A8], r14; __int64
0x180022d69  mov     r9d, [rsp+3C8h+arg_20]
0x180022d71  mov     r8d, [rsp+3C8h+var_378]
0x180022d76  mov     rdx, r12
0x180022d79  lea     rcx, [rsp+3C8h+ArgList]; ArgList
0x180022d81  call    LdrpLoadDllInternal
0x180022d86  nop
0x180022d87  lea     rcx, [rsp+3C8h+var_358]
0x180022d8c  call    RtlDeactivateActivationContextUnsafeFast
0x180022d91  lea     rax, [rsp+3C8h+var_258]
0x180022d99  mov     rcx, [rsp+3C8h+Src]
0x180022da1  cmp     rax, rcx
0x180022da4  jz      short loc_180022DAB
0x180022da6  call    RtlpSysVolFree
0x180022dab  lea     rax, [rsp+3C8h+var_258]
0x180022db3  mov     [rsp+3C8h+Src], rax
0x180022dbb  mov     [rsp+3C8h+var_268], 1000000h
0x180022dc6  mov     [rsp+3C8h+var_258], di
0x180022dce  lea     rax, [rsp+3C8h+var_148]
0x180022dd6  mov     rcx, [rsp+3C8h+var_150]
0x180022dde  cmp     rax, rcx
0x180022de1  jz      short loc_180022DE8
0x180022de3  call    RtlpSysVolFree
0x180022de8  mov     eax, dword ptr [rsp+3C8h+var_374]
0x180022dec  mov     rcx, [rsp+3C8h+var_48]
0x180022df4  xor     rcx, rsp; StackCookie
0x180022df7  call    __security_check_cookie
0x180022dfc  add     rsp, 390h
0x180022e03  pop     r15
0x180022e05  pop     r14
0x180022e07  pop     r13
0x180022e09  pop     r12
0x180022e0b  pop     rdi
0x180022e0c  pop     rsi
0x180022e0d  pop     rbx
0x180022e0e  retn
0x180022e10  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x180022e14  lea     r8, [rsp+3C8h+var_378]
0x180022e19  xor     edx, edx
0x180022e1b  xor     ecx, ecx
0x180022e1d  call    RtlUTF8ToUnicodeN
0x180022e22  mov     edx, [rsp+3C8h+var_378]
0x180022e26  jmp     loc_180022BC9
0x180022e30  test    eax, eax
0x180022e32  jz      loc_180022BC9
0x180022e38  dec     eax
0x180022e3a  movzx   ecx, byte ptr [r9]
0x180022e3e  inc     r9
0x180022e41  cmp     [r8+rcx*2], bx
0x180022e46  jnz     loc_180022ECE
0x180022e4c  add     edx, 2
0x180022e4f  jmp     short loc_180022E30
0x180022e51  mov     eax, [rbx+10h]
0x180022e54  and     al, 70h
0x180022e56  cmp     al, 20h ; ' '
0x180022e58  jz      loc_180022CE3
0x180022e5e  mov     [rsp+3C8h+ExceptionRecord.NumberParameters], 4
0x180022e69  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation], rsi
0x180022e71  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation+8], rbx
0x180022e79  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation+10h], rbx
0x180022e81  mov     eax, [rbx+10h]
0x180022e84  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation+18h], rax
0x180022e8c  mov     [rsp+3C8h+ExceptionRecord.ExceptionCode], 0C0150014h
0x180022e97  mov     [rsp+3C8h+ExceptionRecord.ExceptionFlags], 1
0x180022ea2  lea     rcx, [rsp+3C8h+ExceptionRecord]; ExceptionRecord
0x180022eaa  call    RtlRaiseException
0x180022eaf  jmp     loc_180022D1B
0x180022eb4  cmp     [rbx+8], rdi
0x180022eb8  jz      loc_180022D10
0x180022ebe  lea     rax, [rsp+3C8h+var_348]
0x180022ec6  mov     [rsi], rax
0x180022ec9  jmp     loc_180022D1B
0x180022ece  test    eax, eax
0x180022ed0  jz      loc_180022F90
0x180022ed6  dec     eax
0x180022ed8  inc     r9
0x180022edb  jmp     loc_180022E4C
0x180022ee0  mov     eax, 0FFFEh
0x180022ee5  cmp     r8d, eax
0x180022ee8  ja      loc_180022F86
0x180022eee  lea     edi, [r8+3Fh]
0x180022ef2  and     edi, 0FFFFFFC0h
0x180022ef5  cmp     edi, eax
0x180022ef7  cmova   edi, eax
0x180022efa  mov     ecx, edi
0x180022efc  lea     rax, [rsp+3C8h+var_258]
0x180022f04  mov     rdx, [rsp+3C8h+Src]
0x180022f0c  cmp     rdx, rax
0x180022f0f  jz      short loc_180022F57
0x180022f11  call    NtdllpReallocateStringRoutine
0x180022f16  mov     r15, rax
0x180022f19  movzx   ecx, word ptr [rsp+3C8h+var_268]
0x180022f21  test    r15, r15
0x180022f24  jz      short loc_180022F40
0x180022f26  mov     [rsp+3C8h+Src], r15
0x180022f2e  mov     word ptr [rsp+3C8h+var_268+2], di
0x180022f36  mov     r15, qword ptr [rsp+3C8h+var_374+4]
0x180022f3b  jmp     loc_180022BE9
0x180022f40  mov     ebx, 0C0000017h
0x180022f45  movzx   edi, word ptr [rsp+3C8h+var_268+2]
0x180022f4d  mov     r15, qword ptr [rsp+3C8h+var_374+4]
0x180022f52  jmp     loc_180022BE9
0x180022f57  call    RtlpAllocateAtom
0x180022f5c  mov     r15, rax
0x180022f5f  test    rax, rax
0x180022f62  jz      short loc_180022F19
0x180022f64  movzx   ecx, word ptr [rsp+3C8h+var_268]
0x180022f6c  test    cx, cx
0x180022f6f  jz      short loc_180022F21
0x180022f71  mov     r8d, ecx; Size
0x180022f74  mov     rdx, [rsp+3C8h+Src]; Src
0x180022f7c  mov     rcx, rax; void *
0x180022f7f  call    memmove
0x180022f84  jmp     short loc_180022F19
0x180022f86  mov     ebx, 0C0000106h
0x180022f8b  jmp     loc_180022BE9
0x180022f90  add     edx, 2
0x180022f93  jmp     loc_180022BC9
0x180022f98  xor     ebx, ebx
0x180022f9a  jmp     loc_180022C91
0x180022f9f  test    rbx, rbx
0x180022fa2  jz      loc_180022EBE
0x180022fa8  jmp     loc_180022EB4
0x180165750  push    rbp
0x180165752  sub     rsp, 50h
0x180165756  mov     rbp, rdx
0x180165759  lea     rcx, [rbp+70h]
0x18016575d  call    RtlDeactivateActivationContextUnsafeFast
0x180165762  nop
0x180165763  add     rsp, 50h
0x180165767  pop     rbp
0x180165768  retn
```
