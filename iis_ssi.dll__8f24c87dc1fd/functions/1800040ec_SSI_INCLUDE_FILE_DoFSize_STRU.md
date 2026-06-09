# SSI_INCLUDE_FILE::DoFSize(STRU *)

- ea: `0x1800040ec`
- end: `0x1800042f4`
- name: `?DoFSize@SSI_INCLUDE_FILE@@AEAAJPEAVSTRU@@@Z`
- size: `520`
- prototype: `signed int __fastcall(SSI_INCLUDE_FILE *this, struct STRU *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004afc`

## callees

- `0x180002648`
- `0x1800040ec`
- `0x180005464`
- `0x180005548`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a2`
- `api-ms-win-core-localization-ansi-l1-1-0!GetNumberFormatA` at `0x180004298`
- `api-ms-win-core-localization-ansi-l1-1-0!GetNumberFormatA` at `0x180004298`
- `iisutil!?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z` at `0x180004272`
- `iisutil!?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z` at `0x180004272`

## pseudocode

```c
signed int __fastcall SSI_INCLUDE_FILE::DoFSize(SSI_INCLUDE_FILE *this, struct STRU *a2)
{
  __int64 v2; // r9
  unsigned __int16 *v4; // rax
  __int64 v5; // r9
  int v6; // r8d
  int v7; // ecx
  signed int result; // eax
  struct SSI_FILE *v9; // r15
  int v10; // ebx
  unsigned int v11; // edi
  signed int v12; // r14d
  __int64 v13; // rcx
  int NumberFormatA; // eax
  struct SSI_FILE *v15; // [rsp+30h] [rbp-39h] BYREF
  LPSTR lpNumberStr; // [rsp+38h] [rbp-31h] BYREF
  NUMBERFMTA Format; // [rsp+40h] [rbp-29h] BYREF
  CHAR Value[40]; // [rsp+68h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 10);
  lpNumberStr = 0;
  v4 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
  v5 = v2 - (_QWORD)v4;
  memset(&Format, 0, sizeof(Format));
  do
  {
    v6 = *(unsigned __int16 *)((char *)v4 + v5);
    v7 = *v4 - v6;
    if ( v7 )
      break;
    ++v4;
  }
  while ( v6 );
  v15 = 0;
  if ( v7 )
  {
    result = SSI_FILE::GetReferencedInstance(*((struct SSI_REQUEST **)this + 2), a2, &v15);
    if ( result < 0 )
      return result;
    v9 = v15;
    v15 = 0;
    (*(void (__fastcall **)(_QWORD, struct SSI_FILE **))(**((_QWORD **)v9 + 2) + 64LL))(*((_QWORD *)v9 + 2), &v15);
    v10 = *((_DWORD *)v9 + 10);
    v11 = (unsigned int)v15;
    v12 = HIDWORD(v15) != 0 ? 0x80070032 : 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 2) + 16LL))(*((_QWORD *)v9 + 2));
    if ( !v10 )
      (**(void (__fastcall ***)(struct SSI_FILE *))v9)(v9);
    if ( v12 < 0 )
      return v12;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, struct SSI_FILE **))(**(_QWORD **)(*((_QWORD *)this + 4) + 16LL) + 64LL))(
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL),
      &v15);
    if ( HIDWORD(v15) )
      return -2147024846;
    v11 = (unsigned int)v15;
  }
  if ( !*((_DWORD *)this + 174) )
    v11 = ((v11 & 0x3FF) != 0) + (v11 >> 10);
  *(_QWORD *)&Format.NumDigits = 0;
  Format.lpThousandSep = ",";
  Format.Grouping = 3;
  Format.lpDecimalSep = ".";
  Format.NegativeOrder = 2;
  result = StringCchPrintfA(Value, 0x21u, "%ld", v11);
  if ( result >= 0 )
  {
    v13 = *((_QWORD *)this + 2);
    Value[32] = 0;
    result = CHUNK_BUFFER::AllocateSpace((CHUNK_BUFFER *)(v13 + 800), 0x21u, &lpNumberStr);
    if ( result >= 0 )
    {
      NumberFormatA = GetNumberFormatA(0x800u, 0, Value, &Format, lpNumberStr, 33);
      if ( NumberFormatA )
      {
        return SSI_VECTOR_BUFFER::AddToVector(
                 (SSI_VECTOR_BUFFER *)(*((_QWORD *)this + 2) + 800LL),
                 lpNumberStr,
                 NumberFormatA - 1);
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800040ec  mov     [rsp-8+arg_10], rbx
0x1800040f1  push    rbp
0x1800040f2  push    rsi
0x1800040f3  push    rdi
0x1800040f4  push    r14
0x1800040f6  push    r15
0x1800040f8  lea     rbp, [rsp-37h]
0x1800040fd  sub     rsp, 0A0h
0x180004104  mov     rax, cs:__security_cookie
0x18000410b  xor     rax, rsp
0x18000410e  mov     [rbp+57h+var_30], rax
0x180004112  mov     r9, [rcx+50h]
0x180004116  xor     eax, eax
0x180004118  xorps   xmm0, xmm0
0x18000411b  mov     qword ptr [rbp+57h+Format.NegativeOrder], rax
0x18000411f  mov     [rbp+57h+var_88], rax
0x180004123  mov     rsi, rcx
0x180004126  mov     rax, [rdx+20h]
0x18000412a  sub     r9, rax
0x18000412d  movups  xmmword ptr [rbp+57h+Format.NumDigits], xmm0
0x180004131  movups  xmmword ptr [rbp+57h+Format.lpDecimalSep], xmm0
0x180004135  movzx   ecx, word ptr [rax]
0x180004138  movzx   r8d, word ptr [rax+r9]
0x18000413d  sub     ecx, r8d
0x180004140  jnz     short loc_18000414B
0x180004142  add     rax, 2
0x180004146  test    r8d, r8d
0x180004149  jnz     short loc_180004135
0x18000414b  mov     [rbp+57h+var_90], 0
0x180004153  test    ecx, ecx
0x180004155  jz      short loc_1800041D1
0x180004157  mov     rcx, [rsi+10h]; struct SSI_REQUEST *
0x18000415b  lea     r8, [rbp+57h+var_90]; struct SSI_FILE **
0x18000415f  call    ?GetReferencedInstance@SSI_FILE@@SAJPEAVSSI_REQUEST@@AEAVSTRU@@PEAPEAV1@@Z; SSI_FILE::GetReferencedInstance(SSI_REQUEST *,STRU &,SSI_FILE * *)
0x180004164  test    eax, eax
0x180004166  js      loc_1800042D1
0x18000416c  mov     r15, [rbp+57h+var_90]
0x180004170  lea     rdx, [rbp+57h+var_90]
0x180004174  mov     [rbp+57h+var_90], 0
0x18000417c  mov     rcx, [r15+10h]
0x180004180  mov     rax, [rcx]
0x180004183  mov     rax, [rax+40h]
0x180004187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000418c  mov     ebx, [r15+28h]
0x180004190  mov     rcx, [r15+10h]
0x180004194  mov     eax, dword ptr [rbp+57h+var_90+4]
0x180004197  mov     edi, dword ptr [rbp+57h+var_90]
0x18000419a  neg     eax
0x18000419c  mov     rax, [rcx]
0x18000419f  sbb     r14d, r14d
0x1800041a2  and     r14d, 80070032h
0x1800041a9  mov     rax, [rax+10h]
0x1800041ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b2  test    ebx, ebx
0x1800041b4  jnz     short loc_1800041C4
0x1800041b6  mov     rdx, [r15]
0x1800041b9  mov     rcx, r15
0x1800041bc  mov     rax, [rdx]
0x1800041bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c4  test    r14d, r14d
0x1800041c7  jns     short loc_1800041F6
0x1800041c9  mov     eax, r14d
0x1800041cc  jmp     loc_1800042D1
0x1800041d1  mov     rax, [rsi+20h]
0x1800041d5  lea     rdx, [rbp+57h+var_90]
0x1800041d9  mov     rcx, [rax+10h]
0x1800041dd  mov     rax, [rcx]
0x1800041e0  mov     rax, [rax+40h]
0x1800041e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e9  cmp     dword ptr [rbp+57h+var_90+4], 0
0x1800041ed  jnz     loc_1800042CC
0x1800041f3  mov     edi, dword ptr [rbp+57h+var_90]
0x1800041f6  cmp     dword ptr [rsi+2B8h], 0
0x1800041fd  jnz     short loc_180004212
0x1800041ff  test    edi, 3FFh
0x180004205  mov     ecx, 0
0x18000420a  setnz   cl
0x18000420d  shr     edi, 0Ah
0x180004210  add     edi, ecx
0x180004212  lea     rax, asc_180007F84; ","
0x180004219  mov     qword ptr [rbp+57h+Format.NumDigits], 0
0x180004221  mov     [rbp+57h+Format.lpThousandSep], rax
0x180004225  lea     r8, aLd; "%ld"
0x18000422c  lea     rax, asc_180007F88; "."
0x180004233  mov     [rbp+57h+Format.Grouping], 3
0x18000423a  mov     ebx, 21h ; '!'
0x18000423f  mov     [rbp+57h+Format.lpDecimalSep], rax
0x180004243  mov     r9d, edi
0x180004246  mov     [rbp+57h+Format.NegativeOrder], 2
0x18000424d  mov     edx, ebx; unsigned __int64
0x18000424f  lea     rcx, [rbp+57h+Value]; char *
0x180004253  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180004258  test    eax, eax
0x18000425a  js      short loc_1800042D1
0x18000425c  mov     rcx, [rsi+10h]
0x180004260  lea     r8, [rbp+57h+var_88]
0x180004264  mov     edi, 320h
0x180004269  mov     [rbp+57h+var_38], 0
0x18000426d  add     rcx, rdi
0x180004270  mov     edx, ebx
0x180004272  call    cs:__imp_?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z; CHUNK_BUFFER::AllocateSpace(ulong,char * *)
0x180004278  test    eax, eax
0x18000427a  js      short loc_1800042D1
0x18000427c  mov     rax, [rbp+57h+var_88]
0x180004280  lea     r9, [rbp+57h+Format]; lpFormat
0x180004284  mov     [rsp+0C0h+cchNumber], ebx; cchNumber
0x180004288  lea     r8, [rbp+57h+Value]; lpValue
0x18000428c  xor     edx, edx; dwFlags
0x18000428e  mov     [rsp+0C0h+lpNumberStr], rax; lpNumberStr
0x180004293  mov     ecx, 800h; Locale
0x180004298  call    cs:__imp_GetNumberFormatA
0x18000429e  test    eax, eax
0x1800042a0  jnz     short loc_1800042B6
0x1800042a2  call    cs:__imp_GetLastError
0x1800042a8  test    eax, eax
0x1800042aa  jle     short loc_1800042D1
0x1800042ac  movzx   eax, ax
0x1800042af  or      eax, 80070000h
0x1800042b4  jmp     short loc_1800042D1
0x1800042b6  mov     rcx, [rsi+10h]
0x1800042ba  lea     r8d, [rax-1]; unsigned int
0x1800042be  mov     rdx, [rbp+57h+var_88]; char *
0x1800042c2  add     rcx, rdi; this
0x1800042c5  call    ?AddToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::AddToVector(char *,ulong)
0x1800042ca  jmp     short loc_1800042D1
0x1800042cc  mov     eax, 80070032h
0x1800042d1  mov     rcx, [rbp+57h+var_30]
0x1800042d5  xor     rcx, rsp; StackCookie
0x1800042d8  call    __security_check_cookie
0x1800042dd  mov     rbx, [rsp+0C0h+arg_10]
0x1800042e5  add     rsp, 0A0h
0x1800042ec  pop     r15
0x1800042ee  pop     r14
0x1800042f0  pop     rdi
0x1800042f1  pop     rsi
0x1800042f2  pop     rbp
0x1800042f3  retn
```
