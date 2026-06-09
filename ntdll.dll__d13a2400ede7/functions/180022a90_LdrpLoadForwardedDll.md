# LdrpLoadForwardedDll

- ea: `0x180022a90`
- end: `0x180022f9d`
- name: `LdrpLoadForwardedDll`
- size: `1293`
- prototype: `__int64 __usercall@<rax>(PCANSI_STRING SourceString@<rcx>, int, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18006fd70`
- `0x1800c09fc`

## callees

- `0x1800195a0`
- `0x18001a0d0`
- `0x18001d490`
- `0x18001dc60`
- `0x180021c70`
- `0x180021fd0`
- `0x180022160`
- `0x180022a90`
- `0x180024990`
- `0x180120694`
- `0x180162810`
- `0x180164280`
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
0x180022a90  push    rbx
0x180022a92  push    rsi
0x180022a93  push    rdi
0x180022a94  push    r12
0x180022a96  push    r13
0x180022a98  push    r14
0x180022a9a  push    r15
0x180022a9c  sub     rsp, 390h
0x180022aa3  mov     rax, cs:__security_cookie
0x180022aaa  xor     rax, rsp
0x180022aad  mov     [rsp+3C8h+var_48], rax
0x180022ab5  mov     r14, r9
0x180022ab8  mov     r13, r8
0x180022abb  mov     r12, rdx
0x180022abe  mov     rsi, rcx
0x180022ac1  mov     r15, [rsp+3C8h+arg_28]
0x180022ac9  mov     qword ptr [rsp+3C8h+var_374+4], r15
0x180022ace  xor     eax, eax
0x180022ad0  mov     [rsp+3C8h+var_154], eax
0x180022ad7  xor     edx, edx; Val
0x180022ad9  mov     r8d, 0FEh; Size
0x180022adf  lea     rcx, [rsp+3C8h+var_146]; void *
0x180022ae7  call    memset$thunk$772440563353939046
0x180022aec  xor     edi, edi
0x180022aee  mov     dword ptr [rsp+3C8h+var_374], edi
0x180022af2  xor     eax, eax
0x180022af4  mov     [rsp+3C8h+var_264], eax
0x180022afb  xor     edx, edx; Val
0x180022afd  mov     r8d, 0FEh; Size
0x180022b03  lea     rcx, [rsp+3C8h+var_256]; void *
0x180022b0b  call    memset$thunk$772440563353939046
0x180022b10  lea     rax, [rsp+3C8h+var_148]
0x180022b18  mov     [rsp+3C8h+var_150], rax
0x180022b20  mov     dword ptr [rsp+3C8h+ArgList], 1000000h
0x180022b2b  mov     [rsp+3C8h+var_148], di
0x180022b33  lea     rax, [rsp+3C8h+var_258]
0x180022b3b  mov     [rsp+3C8h+Src], rax
0x180022b43  mov     [rsp+3C8h+var_268], 1000000h
0x180022b4e  mov     [rsp+3C8h+var_258], di
0x180022b56  xorps   xmm0, xmm0
0x180022b59  movups  xmmword ptr [rsp+3C8h+DestinationString.Length], xmm0
0x180022b5e  mov     ebx, edi
0x180022b60  movzx   eax, word ptr [rsi]
0x180022b63  test    ax, ax
0x180022b66  jz      loc_180022C1B
0x180022b6c  mov     [rsp+3C8h+var_378], edi
0x180022b70  mov     r9, [rsi+8]
0x180022b74  lock or [rsp+3C8h+var_3C8], ebx
0x180022b78  mov     ecx, 0FDE9h
0x180022b7d  cmp     cs:word_1801C4FD0, cx
0x180022b84  jz      loc_180022E00
0x180022b8a  cmp     cs:GlobalRtlNlsState, cx
0x180022b91  jz      loc_180022E00
0x180022b97  lock or [rsp+3C8h+var_3C8], ebx
0x180022b9b  mov     edx, edi
0x180022b9d  cmp     cs:word_1801C4F9C, di
0x180022ba4  setnz   cl
0x180022ba7  mov     r8, cs:qword_1801C5020
0x180022bae  test    cl, cl
0x180022bb0  jnz     loc_180022E20
0x180022bb6  lea     edx, [rax+rax]
0x180022bb9  movzx   ecx, word ptr [rsp+3C8h+var_268]
0x180022bc1  lea     r8d, [rcx+2]
0x180022bc5  add     r8d, edx
0x180022bc8  movzx   edi, word ptr [rsp+3C8h+var_268+2]
0x180022bd0  cmp     r8d, edi
0x180022bd3  ja      loc_180022ED0
0x180022bd9  test    ebx, ebx
0x180022bdb  js      short loc_180022C19
0x180022bdd  movzx   eax, cx
0x180022be0  add     rax, [rsp+3C8h+Src]
0x180022be8  mov     [rsp+3C8h+DestinationString.Buffer], rax
0x180022bed  xor     eax, eax
0x180022bef  mov     [rsp+3C8h+DestinationString.Length], ax
0x180022bf4  sub     di, cx
0x180022bf7  mov     [rsp+3C8h+DestinationString.MaximumLength], di
0x180022bfc  xor     r8d, r8d; AllocateDestinationString
0x180022bff  mov     rdx, rsi; SourceString
0x180022c02  lea     rcx, [rsp+3C8h+DestinationString]; DestinationString
0x180022c07  call    RtlAnsiStringToUnicodeString
0x180022c0c  movzx   eax, [rsp+3C8h+DestinationString.Length]
0x180022c11  add     word ptr [rsp+3C8h+var_268], ax
0x180022c19  xor     edi, edi
0x180022c1b  mov     dword ptr [rsp+3C8h+var_374], ebx
0x180022c1f  test    ebx, ebx
0x180022c21  js      loc_180022D81
0x180022c27  mov     [rsp+3C8h+var_358], 48h ; 'H'
0x180022c30  mov     [rsp+3C8h+var_350], 1
0x180022c39  xorps   xmm0, xmm0
0x180022c3c  xor     eax, eax
0x180022c3e  movups  [rsp+3C8h+var_348], xmm0
0x180022c46  movups  [rsp+3C8h+var_338], xmm0
0x180022c4e  movups  [rsp+3C8h+var_328], xmm0
0x180022c56  mov     [rsp+3C8h+var_318], rax
0x180022c5e  mov     rdi, [r14+88h]
0x180022c65  mov     rax, gs:30h
0x180022c6e  mov     rsi, [rax+2C8h]
0x180022c75  test    rsi, rsi
0x180022c78  jz      loc_180022F88
0x180022c7e  mov     rbx, [rsi]
0x180022c81  xor     edx, edx; Val
0x180022c83  mov     r8d, 98h; Size
0x180022c89  lea     rcx, [rsp+3C8h+ExceptionRecord]; void *
0x180022c91  call    memset$thunk$772440563353939046
0x180022c96  cmp     [rsp+3C8h+var_358], 48h ; 'H'
0x180022c9c  jb      short loc_180022CCA
0x180022c9e  mov     rax, rbx
0x180022ca1  not     rax
0x180022ca4  mov     qword ptr [rsp+3C8h+var_338+8], rax
0x180022cac  mov     rax, rdi
0x180022caf  not     rax
0x180022cb2  mov     qword ptr [rsp+3C8h+var_328], rax
0x180022cba  mov     rax, [rsp+3C8h]
0x180022cc2  mov     qword ptr [rsp+3C8h+var_328+8], rax
0x180022cca  test    rbx, rbx
0x180022ccd  jnz     loc_180022E41
0x180022cd3  mov     qword ptr [rsp+3C8h+var_348], rbx
0x180022cdb  mov     qword ptr [rsp+3C8h+var_348+8], rdi
0x180022ce3  mov     dword ptr [rsp+3C8h+var_338], 20h ; ' '
0x180022cee  test    rbx, rbx
0x180022cf1  jnz     loc_180022EA4
0x180022cf7  test    rdi, rdi
0x180022cfa  jnz     loc_180022F8F
0x180022d00  mov     dword ptr [rsp+3C8h+var_338], 30h ; '0'
0x180022d0b  xor     edi, edi
0x180022d0d  mov     [rsp+3C8h+var_378], edi
0x180022d11  lea     r9, [rsp+3C8h+var_378]
0x180022d16  mov     r8, r14
0x180022d19  lea     rdx, [rsp+3C8h+ArgList]
0x180022d21  lea     rcx, [rsp+3C8h+var_268]
0x180022d29  call    LdrpPreprocessDllName
0x180022d2e  mov     dword ptr [rsp+3C8h+var_374], eax
0x180022d32  test    eax, eax
0x180022d34  js      short loc_180022D77
0x180022d36  mov     qword ptr [rsp+3C8h+var_380], rdi; char
0x180022d3b  mov     [rsp+3C8h+var_388], rdi; __int64
0x180022d40  lea     rax, [rsp+3C8h+var_374]
0x180022d45  mov     [rsp+3C8h+var_390], rax; __int64
0x180022d4a  mov     [rsp+3C8h+var_398], r15; __int64
0x180022d4f  mov     [rsp+3C8h+var_3A0], r13; __int64
0x180022d54  mov     [rsp+3C8h+var_3A8], r14; __int64
0x180022d59  mov     r9d, [rsp+3C8h+arg_20]
0x180022d61  mov     r8d, [rsp+3C8h+var_378]
0x180022d66  mov     rdx, r12
0x180022d69  lea     rcx, [rsp+3C8h+ArgList]; ArgList
0x180022d71  call    LdrpLoadDllInternal
0x180022d76  nop
0x180022d77  lea     rcx, [rsp+3C8h+var_358]
0x180022d7c  call    RtlDeactivateActivationContextUnsafeFast
0x180022d81  lea     rax, [rsp+3C8h+var_258]
0x180022d89  mov     rcx, [rsp+3C8h+Src]
0x180022d91  cmp     rax, rcx
0x180022d94  jz      short loc_180022D9B
0x180022d96  call    RtlpSysVolFree
0x180022d9b  lea     rax, [rsp+3C8h+var_258]
0x180022da3  mov     [rsp+3C8h+Src], rax
0x180022dab  mov     [rsp+3C8h+var_268], 1000000h
0x180022db6  mov     [rsp+3C8h+var_258], di
0x180022dbe  lea     rax, [rsp+3C8h+var_148]
0x180022dc6  mov     rcx, [rsp+3C8h+var_150]
0x180022dce  cmp     rax, rcx
0x180022dd1  jz      short loc_180022DD8
0x180022dd3  call    RtlpSysVolFree
0x180022dd8  mov     eax, dword ptr [rsp+3C8h+var_374]
0x180022ddc  mov     rcx, [rsp+3C8h+var_48]
0x180022de4  xor     rcx, rsp; StackCookie
0x180022de7  call    __security_check_cookie
0x180022dec  add     rsp, 390h
0x180022df3  pop     r15
0x180022df5  pop     r14
0x180022df7  pop     r13
0x180022df9  pop     r12
0x180022dfb  pop     rdi
0x180022dfc  pop     rsi
0x180022dfd  pop     rbx
0x180022dfe  retn
0x180022e00  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x180022e04  lea     r8, [rsp+3C8h+var_378]
0x180022e09  xor     edx, edx
0x180022e0b  xor     ecx, ecx
0x180022e0d  call    RtlUTF8ToUnicodeN
0x180022e12  mov     edx, [rsp+3C8h+var_378]
0x180022e16  jmp     loc_180022BB9
0x180022e20  test    eax, eax
0x180022e22  jz      loc_180022BB9
0x180022e28  dec     eax
0x180022e2a  movzx   ecx, byte ptr [r9]
0x180022e2e  inc     r9
0x180022e31  cmp     [r8+rcx*2], bx
0x180022e36  jnz     loc_180022EBE
0x180022e3c  add     edx, 2
0x180022e3f  jmp     short loc_180022E20
0x180022e41  mov     eax, [rbx+10h]
0x180022e44  and     al, 70h
0x180022e46  cmp     al, 20h ; ' '
0x180022e48  jz      loc_180022CD3
0x180022e4e  mov     [rsp+3C8h+ExceptionRecord.NumberParameters], 4
0x180022e59  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation], rsi
0x180022e61  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation+8], rbx
0x180022e69  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation+10h], rbx
0x180022e71  mov     eax, [rbx+10h]
0x180022e74  mov     [rsp+3C8h+ExceptionRecord.ExceptionInformation+18h], rax
0x180022e7c  mov     [rsp+3C8h+ExceptionRecord.ExceptionCode], 0C0150014h
0x180022e87  mov     [rsp+3C8h+ExceptionRecord.ExceptionFlags], 1
0x180022e92  lea     rcx, [rsp+3C8h+ExceptionRecord]; ExceptionRecord
0x180022e9a  call    RtlRaiseException
0x180022e9f  jmp     loc_180022D0B
0x180022ea4  cmp     [rbx+8], rdi
0x180022ea8  jz      loc_180022D00
0x180022eae  lea     rax, [rsp+3C8h+var_348]
0x180022eb6  mov     [rsi], rax
0x180022eb9  jmp     loc_180022D0B
0x180022ebe  test    eax, eax
0x180022ec0  jz      loc_180022F80
0x180022ec6  dec     eax
0x180022ec8  inc     r9
0x180022ecb  jmp     loc_180022E3C
0x180022ed0  mov     eax, 0FFFEh
0x180022ed5  cmp     r8d, eax
0x180022ed8  ja      loc_180022F76
0x180022ede  lea     edi, [r8+3Fh]
0x180022ee2  and     edi, 0FFFFFFC0h
0x180022ee5  cmp     edi, eax
0x180022ee7  cmova   edi, eax
0x180022eea  mov     ecx, edi
0x180022eec  lea     rax, [rsp+3C8h+var_258]
0x180022ef4  mov     rdx, [rsp+3C8h+Src]
0x180022efc  cmp     rdx, rax
0x180022eff  jz      short loc_180022F47
0x180022f01  call    NtdllpReallocateStringRoutine
0x180022f06  mov     r15, rax
0x180022f09  movzx   ecx, word ptr [rsp+3C8h+var_268]
0x180022f11  test    r15, r15
0x180022f14  jz      short loc_180022F30
0x180022f16  mov     [rsp+3C8h+Src], r15
0x180022f1e  mov     word ptr [rsp+3C8h+var_268+2], di
0x180022f26  mov     r15, qword ptr [rsp+3C8h+var_374+4]
0x180022f2b  jmp     loc_180022BD9
0x180022f30  mov     ebx, 0C0000017h
0x180022f35  movzx   edi, word ptr [rsp+3C8h+var_268+2]
0x180022f3d  mov     r15, qword ptr [rsp+3C8h+var_374+4]
0x180022f42  jmp     loc_180022BD9
0x180022f47  call    RtlpAllocateAtom
0x180022f4c  mov     r15, rax
0x180022f4f  test    rax, rax
0x180022f52  jz      short loc_180022F09
0x180022f54  movzx   ecx, word ptr [rsp+3C8h+var_268]
0x180022f5c  test    cx, cx
0x180022f5f  jz      short loc_180022F11
0x180022f61  mov     r8d, ecx; Size
0x180022f64  mov     rdx, [rsp+3C8h+Src]; Src
0x180022f6c  mov     rcx, rax; void *
0x180022f6f  call    memmove
0x180022f74  jmp     short loc_180022F09
0x180022f76  mov     ebx, 0C0000106h
0x180022f7b  jmp     loc_180022BD9
0x180022f80  add     edx, 2
0x180022f83  jmp     loc_180022BB9
0x180022f88  xor     ebx, ebx
0x180022f8a  jmp     loc_180022C81
0x180022f8f  test    rbx, rbx
0x180022f92  jz      loc_180022EAE
0x180022f98  jmp     loc_180022EA4
0x180165f50  push    rbp
0x180165f52  sub     rsp, 50h
0x180165f56  mov     rbp, rdx
0x180165f59  lea     rcx, [rbp+70h]
0x180165f5d  call    RtlDeactivateActivationContextUnsafeFast
0x180165f62  nop
0x180165f63  add     rsp, 50h
0x180165f67  pop     rbp
0x180165f68  retn
```
