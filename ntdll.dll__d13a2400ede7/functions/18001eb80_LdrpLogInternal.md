# LdrpLogInternal

- ea: `0x18001eb80`
- end: `0x18001f05f`
- name: `LdrpLogInternal`
- size: `1247`
- prototype: `__int64 __fastcall(int, int, int, int, char *Format, char ArgList)`
- caller_count: `70`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18001b9b0`
- `0x18001dc60`
- `0x18001e820`
- `0x180023e10`
- `0x180024990`
- `0x180025688`
- `0x180025988`
- `0x180025a40`
- `0x180025abc`
- `0x180025b20`
- `0x180025fb4`
- `0x18002630c`
- `0x180027a70`
- `0x180029010`
- `0x1800298a0`
- `0x180029eb0`
- `0x18002b5f0`
- `0x18002b7b0`
- `0x18002bc70`
- `0x1800376a0`
- `0x18004eb70`
- `0x18004fab0`
- `0x18004ff78`
- `0x180050718`
- `0x1800607d0`
- `0x180069678`
- `0x18006cc40`
- `0x18006d980`
- `0x18006e930`
- `0x18007c7d4`
- `0x180083c30`
- `0x1800847b0`
- `0x180085904`
- `0x180086838`
- `0x1800b6f08`
- `0x1800b7570`
- `0x1800bfe70`
- `0x1800c03e0`
- `0x1800c0b5c`
- `0x1800c0ca0`
- `0x1800c0e80`
- `0x1800c16f0`
- `0x1800c18c0`
- `0x1800c19c0`
- `0x1800c1c4c`
- `0x1800c2338`
- `0x1800c29c0`
- `0x1800c35bc`
- `0x1800ced58`
- `0x1800d1c34`

## callees

- `0x18001eb80`
- `0x18001f4d0`
- `0x1800215e0`
- `0x180022160`
- `0x18006f0d0`
- `0x180111c10`
- `0x18011e690`
- `0x1801285f0`
- `0x180162810`
- `0x18016f030`

## pseudocode

```c
__int64 LdrpLogInternal(int a1, int a2, __int64 a3, int a4, char *Format, ...)
{
  __int64 v6; // rbx
  unsigned int v8; // edi
  int Args; // ecx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int16 v14; // cx
  __int64 *v15; // r11
  __int16 v16; // ax
  char *v17; // r9
  __int64 v18; // r10
  unsigned __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  _DWORD *SharedData; // rcx
  __int64 v24; // rcx
  __int64 result; // rax
  int v26; // ecx
  __int64 v27; // rcx
  __int64 v28; // rax
  char *v29; // rcx
  signed __int32 v30[6]; // [rsp+8h] [rbp-100h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C8h]
  char *v32; // [rsp+48h] [rbp-C0h]
  __int64 v33; // [rsp+58h] [rbp-B0h] BYREF
  int v34[2]; // [rsp+60h] [rbp-A8h] BYREF
  va_list v35; // [rsp+68h] [rbp-A0h]
  _WORD v36[2]; // [rsp+70h] [rbp-98h] BYREF
  int v37; // [rsp+74h] [rbp-94h]
  int *v38; // [rsp+78h] [rbp-90h]
  _WORD v39[2]; // [rsp+80h] [rbp-88h] BYREF
  int v40; // [rsp+84h] [rbp-84h]
  _WORD *v41; // [rsp+88h] [rbp-80h]
  char Buffer[255]; // [rsp+98h] [rbp-70h] BYREF
  char v43; // [rsp+197h] [rbp+8Fh]
  int v44[64]; // [rsp+198h] [rbp+90h] BYREF
  _WORD v45[256]; // [rsp+298h] [rbp+190h] BYREF
  va_list va; // [rsp+520h] [rbp+418h] BYREF

  va_start(va, Format);
  v6 = 2LL * a4;
  va_copy(v35, va);
  v37 = 0;
  v40 = 0;
  if ( (unsigned int)(a4 - 2) > 2 )
  {
    if ( qword_1801CA838 )
    {
      v8 = 256;
      memset_thunk_772440563353939046(v44, 0, 0x100u);
      memset_thunk_772440563353939046(v45, 0, 0x200u);
      v36[1] = 256;
      v38 = v44;
      LODWORD(v33) = 0;
      v39[1] = 512;
      *(_QWORD *)v34 = 0;
      v41 = v45;
      memset_thunk_772440563353939046(Buffer, 0, 0x100u);
      Args = (int)NtCurrentTeb()->ClientId.UniqueThread;
      v32 = (&off_1801701B8)[v6];
      v31 = a3;
      v10 = RtlStringCchPrintfExW((int)v44, 128, 0, (int)v34, 0, (wchar_t *)L"%x-%S-%S-", Args);
      if ( !v10 || v10 == -2147483643 )
      {
        v36[0] = 2 * (128 - LOWORD(v34[0]));
        v11 = vsnprintf(Buffer, 0xFFu, Format, va);
        if ( v11 < 0 || (unsigned __int64)v11 > 0xFF )
        {
          v43 = 0;
          v12 = 1;
        }
        else if ( v11 == 255 )
        {
          v43 = 0;
          v12 = 1;
        }
        else
        {
          v12 = 256 - v11;
        }
        v13 = (unsigned int)(256 - v12);
        v39[0] = 2 * (256 - v12);
        _InterlockedOr(v30, 0);
        if ( word_1801C4FD0 == -535 || GlobalRtlNlsState == -535 )
        {
          v14 = Utf8TableInfo;
          v15 = (__int64 *)&xmmword_1801C5070;
          v16 = WORD6(Utf8TableInfo);
          v17 = (char *)xmmword_1801C5070;
          v18 = qword_1801C5088;
        }
        else
        {
          _InterlockedOr(v30, 0);
          v14 = GlobalRtlNlsState;
          v15 = &qword_1801C4FB0;
          v16 = word_1801C4F9C;
          v17 = (char *)qword_1801C4FB0;
          v18 = qword_1801C4FC8;
        }
        v19 = (unsigned __int64)v45;
        if ( v14 == -535 )
        {
          if ( (_DWORD)v13 )
            RtlUTF8ToUnicodeN((unsigned int)v45, 512, (unsigned int)&v33, (unsigned int)Buffer, v13);
          else
            LODWORD(v33) = 0;
        }
        else if ( v16 )
        {
          v17 = Buffer;
          while ( v8 && (_DWORD)v13 )
          {
            v13 = (unsigned int)(v13 - 1);
            v27 = 2LL * (unsigned __int8)*v17;
            v28 = *(unsigned __int16 *)(v18 + v27);
            if ( (_WORD)v28 )
            {
              if ( !(_DWORD)v13 )
              {
                *(_WORD *)v19 = 0;
                LODWORD(v19) = v19 + 2;
                break;
              }
              v13 = (unsigned int)(v13 - 1);
              --v8;
              *(_WORD *)v19 = *(_WORD *)(v18 + 2 * (v28 + (unsigned __int8)v17[1]));
              v19 += 2LL;
              v17 += 2;
            }
            else
            {
              --v8;
              *(_WORD *)v19 = *(_WORD *)(v27 + *v15);
              v19 += 2LL;
              ++v17;
            }
          }
          v19 = (unsigned int)v19 - (unsigned int)v45;
          LODWORD(v33) = v19;
        }
        else
        {
          v19 = 0;
          if ( (unsigned int)v13 <= 0x100 )
            v8 = v13;
          LODWORD(v33) = 2 * v8;
          if ( v8 )
          {
            do
            {
              v13 = (unsigned int)v19;
              v19 = (unsigned int)(v19 + 1);
              v45[v13] = *(_WORD *)&v17[2 * (unsigned __int8)Buffer[v13]];
            }
            while ( (unsigned int)v19 < v8 );
          }
        }
        LdrpAddUnicodeStringToSnapsBuffer(v36, v13, v19, v17);
        LdrpAddUnicodeStringToSnapsBuffer(v39, v20, v21, v22);
      }
    }
  }
  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
    v24 = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    v24 = 2147353476;
  if ( *(_BYTE *)v24 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    v29 = (unsigned int)RtlGetCurrentServiceSessionId() ? (char *)NtCurrentPeb()->SharedData + 555 : (char *)2147353477;
    if ( *v29 < 0 )
      LdrpEtwLogLoaderSnaps(a3, a4, Format, va);
  }
  result = (unsigned int)LdrpDebugFlags;
  v26 = LdrpLogLevelStateTable[2 * v6] | 1;
  if ( (v26 & LdrpDebugFlags) != 0 && ((LdrpDebugFlags & 0x80u) == 0 || LdrpIsSecureProcess) )
  {
    LdrpLogDbgPrint(v26, a2, a3, a4, (__int64)Format, (__int64)va);
    result = (unsigned int)LdrpDebugFlags;
  }
  if ( ((unsigned int)result & dword_180171484[2 * v6]) != 0 )
    __debugbreak();
  return result;
}

```

## disassembly

```asm
0x18001eb80  mov     [rsp-8+arg_8], edx
0x18001eb84  mov     r11, rsp
0x18001eb87  mov     [r11+8], rcx
0x18001eb8b  push    rbp
0x18001eb8c  lea     rbp, [r11-3E8h]
0x18001eb93  sub     rsp, 4E0h
0x18001eb9a  mov     rax, cs:__security_cookie
0x18001eba1  xor     rax, rsp
0x18001eba4  mov     [rbp+3E0h+var_50], rax
0x18001ebab  mov     [r11-10h], rbx
0x18001ebaf  mov     [r11-18h], rsi
0x18001ebb3  mov     [r11-20h], rdi
0x18001ebb7  lea     rdi, [rbp+3E0h+ArgList]
0x18001ebbe  mov     [r11-30h], r13
0x18001ebc2  xor     r13d, r13d
0x18001ebc5  movsxd  rsi, r9d
0x18001ebc8  mov     [r11-38h], r14
0x18001ebcc  mov     rbx, rsi
0x18001ebcf  add     rbx, rbx
0x18001ebd2  mov     [r11-40h], r15
0x18001ebd6  mov     r15, r8
0x18001ebd9  mov     qword ptr [rsp+4E0h+var_480], rdi
0x18001ebde  lea     eax, [rsi-2]
0x18001ebe1  mov     dword ptr [rsp+4E0h+var_478+4], r13d
0x18001ebe6  mov     [rsp+4E0h+var_464], r13d
0x18001ebeb  lea     r14, cs:180000000h
0x18001ebf2  cmp     eax, 2
0x18001ebf5  jbe     loc_18001EDF9
0x18001ebfb  cmp     cs:qword_1801CA838, r13
0x18001ec02  jz      loc_18001EDF9
0x18001ec08  mov     [r11-28h], r12
0x18001ec0c  lea     rcx, [rbp+3E0h+var_350]; void *
0x18001ec13  mov     r12, [rbp+3E0h+Format]
0x18001ec1a  mov     edi, 100h
0x18001ec1f  mov     r8d, edi; Size
0x18001ec22  xor     edx, edx; Val
0x18001ec24  call    memset$thunk$772440563353939046
0x18001ec29  xor     edx, edx; Val
0x18001ec2b  lea     rcx, [rbp+3E0h+var_250]; void *
0x18001ec32  mov     r8d, 200h; Size
0x18001ec38  call    memset$thunk$772440563353939046
0x18001ec3d  lea     rax, [rbp+3E0h+var_350]
0x18001ec44  mov     word ptr [rsp+4E0h+var_478+2], di
0x18001ec49  mov     qword ptr [rsp+4E0h+var_470], rax
0x18001ec4e  lea     rcx, [rbp+3E0h+Buffer]; void *
0x18001ec52  mov     eax, 200h
0x18001ec57  mov     dword ptr [rsp+4E0h+var_490], r13d
0x18001ec5c  mov     [rsp+7Ah], ax
0x18001ec61  mov     r8d, edi; Size
0x18001ec64  lea     rax, [rbp+3E0h+var_250]
0x18001ec6b  mov     qword ptr [rsp+4E0h+var_488], r13
0x18001ec70  xor     edx, edx; Val
0x18001ec72  mov     [rbp+3E0h+var_460], rax
0x18001ec76  call    memset$thunk$772440563353939046
0x18001ec7b  mov     rcx, gs:48h
0x18001ec84  lea     r9, [rsp+4E0h+var_488]; int
0x18001ec89  mov     rax, ds:rva off_1801701B8[r14+rbx*8]; "ERR" ...
0x18001ec91  xor     r8d, r8d; int
0x18001ec94  mov     [rsp+4E0h+var_4A0], rax
0x18001ec99  mov     r14d, 80h
0x18001ec9f  mov     [rsp+4E0h+var_4A8], r15
0x18001eca4  lea     rax, aXSS; "%x-%S-%S-"
0x18001ecab  mov     dword ptr [rsp+4E0h+Args], ecx; Args
0x18001ecaf  mov     edx, r14d; int
0x18001ecb2  mov     [rsp+4E0h+var_4B8], rax; Format
0x18001ecb7  lea     rcx, [rbp+3E0h+var_350]; int
0x18001ecbe  mov     qword ptr [rsp+4E0h+var_4C0], r13; int
0x18001ecc3  call    RtlStringCchPrintfExW
0x18001ecc8  test    eax, eax
0x18001ecca  jnz     loc_18001EEC7
0x18001ecd0  sub     r14w, word ptr [rsp+4E0h+var_488]
0x18001ecd6  lea     r9, [rbp+3E0h+ArgList]; ArgList
0x18001ecdd  add     r14w, r14w
0x18001ece1  lea     rcx, [rbp+3E0h+Buffer]; Buffer
0x18001ece5  mov     r8, r12; Format
0x18001ece8  mov     word ptr [rsp+4E0h+var_478], r14w
0x18001ecee  mov     edx, 0FFh; BufferCount
0x18001ecf3  call    _vsnprintf
0x18001ecf8  test    eax, eax
0x18001ecfa  js      loc_18001EED7
0x18001ed00  movsxd  rcx, eax
0x18001ed03  cmp     rcx, 0FFh
0x18001ed0a  ja      loc_18001EED7
0x18001ed10  mov     edx, r13d
0x18001ed13  jz      loc_18001EFB3
0x18001ed19  mov     rax, rdi
0x18001ed1c  sub     rax, rcx
0x18001ed1f  test    edx, edx
0x18001ed21  jnz     loc_18001EFCD
0x18001ed27  mov     edx, edi
0x18001ed29  sub     edx, eax
0x18001ed2b  movzx   eax, dx
0x18001ed2e  add     ax, ax
0x18001ed31  mov     [rsp+78h], ax
0x18001ed36  lock or [rsp+0], r13d
0x18001ed3b  mov     r14d, 0FDE9h
0x18001ed41  cmp     cs:word_1801C4FD0, r14w
0x18001ed49  jz      loc_18001EE9F
0x18001ed4f  cmp     cs:GlobalRtlNlsState, r14w
0x18001ed57  jz      loc_18001EE9F
0x18001ed5d  lock or [rsp+0], r13d
0x18001ed62  movzx   ecx, cs:GlobalRtlNlsState
0x18001ed69  lea     r11, qword_1801C4FB0
0x18001ed70  movzx   eax, cs:word_1801C4F9C
0x18001ed77  mov     r9, cs:qword_1801C4FB0
0x18001ed7e  mov     r10, cs:qword_1801C4FC8
0x18001ed85  lea     r8, [rbp+3E0h+var_250]
0x18001ed8c  cmp     cx, r14w
0x18001ed90  jz      loc_18001EF8C
0x18001ed96  test    ax, ax
0x18001ed99  jnz     loc_18001EEED
0x18001ed9f  cmp     edx, edi
0x18001eda1  mov     r8d, r13d
0x18001eda4  cmovbe  edi, edx
0x18001eda7  lea     eax, [rdi+rdi]
0x18001edaa  mov     dword ptr [rsp+4E0h+var_490], eax
0x18001edae  test    edi, edi
0x18001edb0  jz      short loc_18001EDCF
0x18001edb2  mov     edx, r8d
0x18001edb5  inc     r8d
0x18001edb8  movzx   eax, [rbp+rdx+3E0h+Buffer]
0x18001edbd  movzx   ecx, word ptr [r9+rax*2]
0x18001edc2  mov     [rbp+rdx*2+3E0h+var_250], cx
0x18001edca  cmp     r8d, edi
0x18001edcd  jb      short loc_18001EDB2
0x18001edcf  lea     rcx, [rsp+4E0h+var_478]
0x18001edd4  call    LdrpAddUnicodeStringToSnapsBuffer
0x18001edd9  lea     rcx, [rsp+78h]
0x18001edde  call    LdrpAddUnicodeStringToSnapsBuffer
0x18001ede3  mov     r12, [rsp+4E0h+var_20]
0x18001edeb  lea     r14, cs:180000000h
0x18001edf2  lea     rdi, [rbp+3E0h+ArgList]
0x18001edf9  mov     rax, gs:60h
0x18001ee02  mov     rcx, [rax+90h]
0x18001ee09  test    rcx, rcx
0x18001ee0c  jnz     loc_18001EF3F
0x18001ee12  mov     ecx, 7FFE0384h
0x18001ee17  cmp     [rcx], r13b
0x18001ee1a  jz      short loc_18001EE32
0x18001ee1c  mov     rax, gs:60h
0x18001ee25  test    byte ptr [rax+378h], 4
0x18001ee2c  jnz     loc_18001EFDE
0x18001ee32  mov     ecx, ds:rva LdrpLogLevelStateTable[r14+rbx*8]
0x18001ee3a  mov     eax, cs:LdrpDebugFlags
0x18001ee40  or      ecx, 1
0x18001ee43  test    eax, ecx
0x18001ee45  jnz     loc_18001F020
0x18001ee4b  test    ds:rva dword_180171484[r14+rbx*8], eax
0x18001ee53  mov     r14, [rsp+4E0h+var_30]
0x18001ee5b  mov     rbx, [rsp+4D8h]
0x18001ee63  mov     r15, [rsp+4E0h+var_38]
0x18001ee6b  mov     r13, [rsp+4E0h+var_28]
0x18001ee73  mov     rdi, [rsp+4E0h+var_18]
0x18001ee7b  mov     rsi, [rsp+4E0h+var_10]
0x18001ee83  jz      short loc_18001EE86
0x18001ee85  int     3; Trap to Debugger
0x18001ee86  mov     rcx, [rbp+3E0h+var_50]
0x18001ee8d  xor     rcx, rsp; StackCookie
0x18001ee90  call    __security_check_cookie
0x18001ee95  add     rsp, 4E0h
0x18001ee9c  pop     rbp
0x18001ee9d  retn
0x18001ee9f  movzx   ecx, word ptr cs:Utf8TableInfo
0x18001eea6  lea     r11, xmmword_1801C5070
0x18001eead  movzx   eax, word ptr cs:Utf8TableInfo+0Ch
0x18001eeb4  mov     r9, qword ptr cs:xmmword_1801C5070
0x18001eebb  mov     r10, cs:qword_1801C5088
0x18001eec2  jmp     loc_18001ED85
0x18001eec7  cmp     eax, 80000005h
0x18001eecc  jnz     loc_18001EDE3
0x18001eed2  jmp     loc_18001ECD0
0x18001eed7  mov     [rbp+3E0h+var_351], r13b
0x18001eede  mov     edx, 80000005h
0x18001eee3  mov     eax, 1
0x18001eee8  jmp     loc_18001ED1F
0x18001eeed  lea     r9, [rbp+3E0h+Buffer]
0x18001eef1  test    edi, edi
0x18001eef3  jz      short loc_18001EF2B
0x18001eef5  test    edx, edx
0x18001eef7  jz      short loc_18001EF2B
0x18001eef9  movzx   eax, byte ptr [r9]
0x18001eefd  dec     edx
0x18001eeff  lea     rcx, [rax+rax]
0x18001ef03  movzx   eax, word ptr [r10+rcx]
0x18001ef08  test    ax, ax
0x18001ef0b  jnz     short loc_18001EF64
0x18001ef0d  mov     rax, [r11]
0x18001ef10  dec     edi
0x18001ef12  movzx   ecx, word ptr [rcx+rax]
0x18001ef16  mov     [r8], cx
0x18001ef1a  add     r8, 2
0x18001ef1e  inc     r9
0x18001ef21  jmp     short loc_18001EEF1
0x18001ef23  mov     [r8], r13w
0x18001ef27  add     r8, 2
0x18001ef2b  lea     rax, [rbp+3E0h+var_250]
0x18001ef32  sub     r8d, eax
0x18001ef35  mov     dword ptr [rsp+4E0h+var_490], r8d
0x18001ef3a  jmp     loc_18001EDCF
0x18001ef3f  cmp     [rcx], r13d
0x18001ef42  jz      loc_18001EE12
0x18001ef48  mov     rax, gs:60h
0x18001ef51  mov     rcx, [rax+90h]
0x18001ef58  add     rcx, 22Ah
0x18001ef5f  jmp     loc_18001EE17
0x18001ef64  test    edx, edx
0x18001ef66  jz      short loc_18001EF23
0x18001ef68  movzx   ecx, byte ptr [r9+1]
0x18001ef6d  inc     r9
0x18001ef70  add     rcx, rax
0x18001ef73  dec     edx
0x18001ef75  dec     edi
0x18001ef77  movzx   eax, word ptr [r10+rcx*2]
0x18001ef7c  mov     [r8], ax
0x18001ef80  add     r8, 2
0x18001ef84  inc     r9
0x18001ef87  jmp     loc_18001EEF1
0x18001ef8c  test    edx, edx
0x18001ef8e  jz      short loc_18001EFC3
0x18001ef90  mov     [rsp+4E0h+var_4C0], edx
0x18001ef94  lea     r9, [rbp+3E0h+Buffer]
0x18001ef98  mov     edx, 200h
0x18001ef9d  lea     r8, [rsp+4E0h+var_490]
0x18001efa2  lea     rcx, [rbp+3E0h+var_250]
0x18001efa9  call    RtlUTF8ToUnicodeN
0x18001efae  jmp     loc_18001EDCF
0x18001efb3  mov     [rbp+3E0h+var_351], dl
0x18001efb9  mov     eax, 1
0x18001efbe  jmp     loc_18001ED1F
0x18001efc3  mov     dword ptr [rsp+4E0h+var_490], r13d
0x18001efc8  jmp     loc_18001EDCF
0x18001efcd  cmp     edx, 80000005h
0x18001efd3  jz      loc_18001ED27
0x18001efd9  jmp     loc_18001EDE3
0x18001efde  call    RtlGetCurrentServiceSessionId
0x18001efe3  test    eax, eax
0x18001efe5  jz      short loc_18001F058
0x18001efe7  mov     rax, gs:60h
0x18001eff0  mov     rcx, [rax+90h]
0x18001eff7  add     rcx, 22Bh
0x18001effe  cmp     [rcx], r13b
0x18001f001  jge     loc_18001EE32
0x18001f007  mov     r8, [rbp+3E0h+Format]; Format
0x18001f00e  mov     r9, rdi; ArgList
0x18001f011  mov     edx, esi; int
0x18001f013  mov     rcx, r15; int
0x18001f016  call    LdrpEtwLogLoaderSnaps
0x18001f01b  jmp     loc_18001EE32
0x18001f020  test    al, al
0x18001f022  jns     short loc_18001F031
0x18001f024  cmp     cs:LdrpIsSecureProcess, r13b
0x18001f02b  jz      loc_18001EE4B
0x18001f031  mov     rax, [rbp+3E0h+Format]
0x18001f038  mov     r9d, esi
0x18001f03b  mov     [rsp+4E0h+var_4B8], rdi
0x18001f040  mov     r8, r15
0x18001f043  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x18001f048  call    LdrpLogDbgPrint
0x18001f04d  mov     eax, cs:LdrpDebugFlags
0x18001f053  jmp     loc_18001EE4B
0x18001f058  mov     ecx, 7FFE0385h
0x18001f05d  jmp     short loc_18001EFFE
```
