# EtwDemux_ParseGuid

- ea: `0x18001a020`
- end: `0x18001a473`
- name: `EtwDemux_ParseGuid`
- size: `1107`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000c974`
- `0x1800191c0`
- `0x180042760`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000abb8`
- `0x18000ac44`
- `0x18001a020`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a10f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a27b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a317`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a3ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a10f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a27b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a317`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001a3ab`

## string_xrefs

- `0x18001a104`: `mpunits.dll`
- `0x18001a26d`: `mpunits.dll`
- `0x18001a30c`: `mpunits.dll`
- `0x18001a3a0`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwDemux_ParseGuid(__int16 *a1, char *a2)
{
  __int16 *v2; // rbx
  unsigned __int64 v3; // rax
  bool v5; // zf
  HMODULE v6; // rax
  int ResultCallback; // eax
  char v8; // r8
  int v9; // r9d
  int v10; // r10d
  __int16 v11; // cx
  char v12; // al
  char v13; // r8
  __int64 v14; // rax
  char v15; // cl
  char v16; // al
  char v17; // cl
  char v18; // al
  char v19; // cl
  char v20; // al
  char v21; // cl
  __int64 result; // rax
  HMODULE v23; // rax
  HMODULE ModuleHandleA; // rax
  HMODULE v25; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-30h] BYREF
  int v27; // [rsp+40h] [rbp-20h]
  int v28; // [rsp+44h] [rbp-1Ch]

  v2 = a1;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 <= 0x26 )
  {
    if ( v3 == 38 )
    {
      if ( (*a1 == 123 && a1[37] == 125 || *a1 == 40 && a1[37] == 41) && a1[9] == 45 && a1[14] == 45 && a1[19] == 45 )
      {
        v5 = a1[24] == 45;
        goto LABEL_13;
      }
    }
    else
    {
      if ( v3 != 36 )
      {
        if ( v3 > 0x20 )
          goto LABEL_21;
        if ( v3 < 0x20 )
        {
LABEL_44:
          *(_DWORD *)&EventDescriptor.Level = 4;
          *(_DWORD *)&EventDescriptor.Id = 3;
          EventDescriptor.Keyword = 1;
          Etw_Trace1_LPCWSTR(&EventDescriptor, (ULONGLONG)a1);
          EventDescriptor = 0;
          ModuleHandleA = GetModuleHandleA("mpunits.dll");
          *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2034, a1);
          LOBYTE(EventDescriptor.Keyword) = 1;
          MI_ReportErrorDetails_ForCustomError(3, (int)L"ETW Normalizer", 0, 0);
          if ( NITS_PRESENCE_STUB != 1 )
          {
            ResultCallback = JobQueryResultCallback();
            v27 = 159;
            goto LABEL_48;
          }
          return 4;
        }
LABEL_24:
        v8 = 0;
        v9 = 0;
        v10 = 0;
        if ( *a1 )
        {
          while ( 1 )
          {
            v11 = *v2;
            if ( *v2 != 123 && v11 != 125 && (unsigned __int16)(v11 - 40) > 1u && v11 != 45 )
            {
              if ( (unsigned __int16)(v11 - 48) > 9u )
              {
                if ( (unsigned __int16)(v11 - 97) > 5u )
                {
                  if ( (unsigned __int16)(v11 - 65) > 5u )
                  {
                    *(_DWORD *)&EventDescriptor.Id = 1;
                    *(_DWORD *)&EventDescriptor.Level = 4;
                    EventDescriptor.Keyword = 1;
                    Etw_Trace1_LPCWSTR(&EventDescriptor, (ULONGLONG)a1);
                    EventDescriptor = 0;
                    v23 = GetModuleHandleA("mpunits.dll");
                    *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(v23, 2032, a1);
                    LOBYTE(EventDescriptor.Keyword) = 1;
                    MI_ReportErrorDetails_ForCustomError(1, (int)L"ETW Normalizer", 0, 0);
                    if ( NITS_PRESENCE_STUB == 1 )
                      return 4;
                    ResultCallback = JobQueryResultCallback();
                    v27 = 179;
LABEL_48:
                    *(_QWORD *)&EventDescriptor.Id = 0;
                    EventDescriptor.Keyword = (ULONGLONG)"admin\\wmi\\winomi\\mp\\etw\\demux.c";
                    v28 = -1;
                    AssertW_Checked(
                      ResultCallback == 0,
                      (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
                      (int)L"Ignoring error deliberately",
                      (int)&EventDescriptor,
                      0);
                    return 4;
                  }
                  v12 = *(_BYTE *)v2 - 55;
                }
                else
                {
                  v12 = *(_BYTE *)v2 - 87;
                }
              }
              else
              {
                v12 = v11 - 48;
              }
              v13 = v12 + v8;
              if ( v9 >= 16 )
                goto LABEL_46;
              if ( v10 )
              {
                v14 = v9;
                v10 = 0;
                ++v9;
                a2[v14] = v13;
                v8 = 0;
              }
              else
              {
                v8 = 16 * v13;
                v10 = 1;
              }
            }
            if ( !*++v2 )
            {
              if ( v9 != 16 )
                goto LABEL_44;
              v15 = *a2;
              *a2 = a2[3];
              v16 = a2[2];
              a2[3] = v15;
              v17 = a2[1];
              a2[1] = v16;
              v18 = a2[5];
              a2[2] = v17;
              v19 = a2[4];
              a2[4] = v18;
              v20 = a2[7];
              a2[5] = v19;
              v21 = a2[6];
              a2[6] = v20;
              result = 0;
              a2[7] = v21;
              return result;
            }
          }
        }
        goto LABEL_44;
      }
      if ( a1[8] == 45 && a1[13] == 45 && a1[18] == 45 )
      {
        v5 = a1[23] == 45;
LABEL_13:
        if ( !v5 )
          goto LABEL_21;
        goto LABEL_24;
      }
    }
LABEL_21:
    *(_DWORD *)&EventDescriptor.Id = 10;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace1_int(&EventDescriptor, (int)a1);
    EventDescriptor = 0;
    v6 = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(v6, 2123, v2);
    LOBYTE(EventDescriptor.Keyword) = 1;
    MI_ReportErrorDetails_ForCustomError(1, (int)L"ETW Normalizer", 0, 0);
    if ( NITS_PRESENCE_STUB != 1 )
    {
      ResultCallback = JobQueryResultCallback();
      v27 = 149;
      goto LABEL_48;
    }
    return 4;
  }
LABEL_46:
  *(_DWORD *)&EventDescriptor.Id = 2;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  Etw_Trace1_LPCWSTR(&EventDescriptor, (ULONGLONG)a1);
  EventDescriptor = 0;
  v25 = GetModuleHandleA("mpunits.dll");
  *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(v25, 2033, a1);
  LOBYTE(EventDescriptor.Keyword) = 1;
  MI_ReportErrorDetails_ForCustomError(2, (int)L"ETW Normalizer", 0, 0);
  if ( NITS_PRESENCE_STUB != 1 )
  {
    ResultCallback = JobQueryResultCallback();
    v27 = 169;
    goto LABEL_48;
  }
  return 4;
}

```

## disassembly

```asm
0x18001a020  mov     [rsp-38h+arg_10], rbx
0x18001a025  push    rbp
0x18001a026  push    rsi
0x18001a027  push    rdi
0x18001a028  push    r12
0x18001a02a  push    r13
0x18001a02c  push    r14
0x18001a02e  push    r15
0x18001a030  mov     rbp, rsp
0x18001a033  sub     rsp, 60h
0x18001a037  mov     rax, cs:__security_cookie
0x18001a03e  xor     rax, rsp
0x18001a041  mov     [rbp+var_10], rax
0x18001a045  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001a049  mov     rbx, rcx
0x18001a04c  mov     rax, r12
0x18001a04f  xor     esi, esi
0x18001a051  mov     rdi, rcx
0x18001a054  inc     rax
0x18001a057  cmp     [rcx+rax*2], si
0x18001a05b  jnz     short loc_18001A054
0x18001a05d  mov     r14d, 1
0x18001a063  lea     r15d, [r14+4]
0x18001a067  lea     r13d, [r14+1]
0x18001a06b  cmp     rax, 26h ; '&'
0x18001a06f  ja      loc_18001A382
0x18001a075  mov     r11w, 2Dh ; '-'
0x18001a07a  jnz     short loc_18001A0B8
0x18001a07c  cmp     word ptr [rcx], 7Bh ; '{'
0x18001a080  jnz     short loc_18001A089
0x18001a082  cmp     word ptr [rcx+4Ah], 7Dh ; '}'
0x18001a087  jz      short loc_18001A096
0x18001a089  cmp     word ptr [rcx], 28h ; '('
0x18001a08d  jnz     short loc_18001A0E4
0x18001a08f  cmp     word ptr [rcx+4Ah], 29h ; ')'
0x18001a094  jnz     short loc_18001A0E4
0x18001a096  cmp     [rcx+12h], r11w
0x18001a09b  jnz     short loc_18001A0E4
0x18001a09d  cmp     [rcx+1Ch], r11w
0x18001a0a2  jnz     short loc_18001A0E4
0x18001a0a4  cmp     [rcx+26h], r11w
0x18001a0a9  jnz     short loc_18001A0E4
0x18001a0ab  cmp     [rcx+30h], r11w
0x18001a0b0  jz      loc_18001A181
0x18001a0b6  jmp     short loc_18001A0E4
0x18001a0b8  cmp     rax, 24h ; '$'
0x18001a0bc  jnz     short loc_18001A0DA
0x18001a0be  cmp     [rcx+10h], r11w
0x18001a0c3  jnz     short loc_18001A0E4
0x18001a0c5  cmp     [rcx+1Ah], r11w
0x18001a0ca  jnz     short loc_18001A0E4
0x18001a0cc  cmp     [rcx+24h], r11w
0x18001a0d1  jnz     short loc_18001A0E4
0x18001a0d3  cmp     [rcx+2Eh], r11w
0x18001a0d8  jmp     short loc_18001A0B0
0x18001a0da  cmp     rax, 20h ; ' '
0x18001a0de  jbe     loc_18001A17B
0x18001a0e4  mov     edx, ebx
0x18001a0e6  mov     dword ptr [rbp+EventDescriptor.Id], 0Ah
0x18001a0ed  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001a0f1  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001a0f8  mov     [rbp+EventDescriptor.Keyword], r14
0x18001a0fc  call    Etw_Trace1_int
0x18001a101  xorps   xmm0, xmm0
0x18001a104  lea     rcx, ModuleName; "mpunits.dll"
0x18001a10b  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a10f  call    cs:__imp_GetModuleHandleA
0x18001a115  mov     r8, rbx
0x18001a118  mov     edx, 84Bh
0x18001a11d  mov     rcx, rax
0x18001a120  call    _Intlstr_FormatString_FormatMessage
0x18001a125  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001a129  lea     r9, [rbp+EventDescriptor]
0x18001a12d  mov     byte ptr [rbp+EventDescriptor.Keyword], r14b
0x18001a131  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001a138  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001a13c  mov     r8d, r15d
0x18001a13f  mov     [rsp+60h+var_38], rsi; __int64
0x18001a144  mov     ecx, r14d; int
0x18001a147  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a14c  mov     [rsp+60h+var_40], rsi; __int64
0x18001a151  call    MI_ReportErrorDetails_ForCustomError
0x18001a156  cmp     cs:NITS_PRESENCE_STUB, r14
0x18001a15d  jz      loc_18001A44A
0x18001a163  mov     rax, cs:off_180047AB8
0x18001a16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a16f  mov     [rbp+var_20], 95h
0x18001a176  jmp     loc_18001A40E
0x18001a17b  jb      loc_18001A2EA
0x18001a181  mov     r8b, sil
0x18001a184  mov     r9d, esi
0x18001a187  mov     r10d, esi
0x18001a18a  cmp     [rcx], si
0x18001a18d  jz      loc_18001A2EA
0x18001a193  movzx   ecx, word ptr [rbx]
0x18001a196  cmp     cx, 7Bh ; '{'
0x18001a19a  jz      short loc_18001A208
0x18001a19c  cmp     cx, 7Dh ; '}'
0x18001a1a0  jz      short loc_18001A208
0x18001a1a2  lea     eax, [rcx-28h]
0x18001a1a5  cmp     ax, r14w
0x18001a1a9  jbe     short loc_18001A208
0x18001a1ab  cmp     cx, r11w
0x18001a1af  jz      short loc_18001A208
0x18001a1b1  lea     eax, [rcx-30h]
0x18001a1b4  cmp     ax, 9
0x18001a1b8  ja      short loc_18001A1C0
0x18001a1ba  mov     al, cl
0x18001a1bc  sub     al, 30h ; '0'
0x18001a1be  jmp     short loc_18001A1DD
0x18001a1c0  lea     eax, [rcx-61h]
0x18001a1c3  cmp     ax, r15w
0x18001a1c7  ja      short loc_18001A1CF
0x18001a1c9  mov     al, [rbx]
0x18001a1cb  sub     al, 57h ; 'W'
0x18001a1cd  jmp     short loc_18001A1DD
0x18001a1cf  sub     cx, 41h ; 'A'
0x18001a1d3  cmp     cx, r15w
0x18001a1d7  ja      short loc_18001A24F
0x18001a1d9  mov     al, [rbx]
0x18001a1db  sub     al, 37h ; '7'
0x18001a1dd  add     r8b, al
0x18001a1e0  cmp     r9d, 10h
0x18001a1e4  jge     loc_18001A382
0x18001a1ea  test    r10d, r10d
0x18001a1ed  jz      short loc_18001A201
0x18001a1ef  movsxd  rax, r9d
0x18001a1f2  mov     r10d, esi
0x18001a1f5  add     r9d, r14d
0x18001a1f8  mov     [rax+rdx], r8b
0x18001a1fc  mov     r8b, sil
0x18001a1ff  jmp     short loc_18001A208
0x18001a201  shl     r8b, 4
0x18001a205  mov     r10d, r14d
0x18001a208  add     rbx, r13
0x18001a20b  cmp     [rbx], si
0x18001a20e  jnz     short loc_18001A193
0x18001a210  cmp     r9d, 10h
0x18001a214  jnz     loc_18001A2EA
0x18001a21a  mov     al, [rdx+3]
0x18001a21d  mov     cl, [rdx]
0x18001a21f  mov     [rdx], al
0x18001a221  mov     al, [rdx+2]
0x18001a224  mov     [rdx+3], cl
0x18001a227  mov     cl, [rdx+1]
0x18001a22a  mov     [rdx+1], al
0x18001a22d  mov     al, [rdx+5]
0x18001a230  mov     [rdx+2], cl
0x18001a233  mov     cl, [rdx+4]
0x18001a236  mov     [rdx+4], al
0x18001a239  mov     al, [rdx+7]
0x18001a23c  mov     [rdx+5], cl
0x18001a23f  mov     cl, [rdx+6]
0x18001a242  mov     [rdx+6], al
0x18001a245  xor     eax, eax
0x18001a247  mov     [rdx+7], cl
0x18001a24a  jmp     loc_18001A44F
0x18001a24f  mov     rdx, rdi
0x18001a252  mov     dword ptr [rbp+EventDescriptor.Id], r14d
0x18001a256  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001a25a  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001a261  mov     [rbp+EventDescriptor.Keyword], r14
0x18001a265  call    Etw_Trace1_LPCWSTR
0x18001a26a  movzx   ebx, word ptr [rbx]
0x18001a26d  lea     rcx, ModuleName; "mpunits.dll"
0x18001a274  xorps   xmm0, xmm0
0x18001a277  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a27b  call    cs:__imp_GetModuleHandleA
0x18001a281  mov     r9d, ebx
0x18001a284  mov     r8, rdi
0x18001a287  mov     rcx, rax
0x18001a28a  mov     edx, 7F0h
0x18001a28f  call    _Intlstr_FormatString_FormatMessage
0x18001a294  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001a298  lea     r9, [rbp+EventDescriptor]
0x18001a29c  mov     byte ptr [rbp+EventDescriptor.Keyword], r14b
0x18001a2a0  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001a2a7  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001a2ab  mov     r8d, r15d
0x18001a2ae  mov     [rsp+60h+var_38], rsi; __int64
0x18001a2b3  mov     ecx, r14d; int
0x18001a2b6  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a2bb  mov     [rsp+60h+var_40], rsi; __int64
0x18001a2c0  call    MI_ReportErrorDetails_ForCustomError
0x18001a2c5  cmp     cs:NITS_PRESENCE_STUB, r14
0x18001a2cc  jz      loc_18001A44A
0x18001a2d2  mov     rax, cs:off_180047AB8
0x18001a2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2de  mov     [rbp+var_20], 0B3h
0x18001a2e5  jmp     loc_18001A40E
0x18001a2ea  mov     ebx, 3
0x18001a2ef  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001a2f6  mov     rdx, rdi
0x18001a2f9  mov     dword ptr [rbp+EventDescriptor.Id], ebx
0x18001a2fc  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001a300  mov     [rbp+EventDescriptor.Keyword], r14
0x18001a304  call    Etw_Trace1_LPCWSTR
0x18001a309  xorps   xmm0, xmm0
0x18001a30c  lea     rcx, ModuleName; "mpunits.dll"
0x18001a313  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a317  call    cs:__imp_GetModuleHandleA
0x18001a31d  mov     r8, rdi
0x18001a320  mov     edx, 7F2h
0x18001a325  mov     rcx, rax
0x18001a328  call    _Intlstr_FormatString_FormatMessage
0x18001a32d  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001a331  lea     r9, [rbp+EventDescriptor]
0x18001a335  mov     byte ptr [rbp+EventDescriptor.Keyword], r14b
0x18001a339  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001a340  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001a344  mov     r8d, r15d
0x18001a347  mov     [rsp+60h+var_38], rsi; __int64
0x18001a34c  mov     ecx, ebx; int
0x18001a34e  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a353  mov     [rsp+60h+var_40], rsi; __int64
0x18001a358  call    MI_ReportErrorDetails_ForCustomError
0x18001a35d  cmp     cs:NITS_PRESENCE_STUB, r14
0x18001a364  jz      loc_18001A44A
0x18001a36a  mov     rax, cs:off_180047AB8
0x18001a371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a376  mov     [rbp+var_20], 9Fh
0x18001a37d  jmp     loc_18001A40E
0x18001a382  mov     rdx, rdi
0x18001a385  mov     dword ptr [rbp+EventDescriptor.Id], r13d
0x18001a389  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001a38d  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001a394  mov     [rbp+EventDescriptor.Keyword], r14
0x18001a398  call    Etw_Trace1_LPCWSTR
0x18001a39d  xorps   xmm0, xmm0
0x18001a3a0  lea     rcx, ModuleName; "mpunits.dll"
0x18001a3a7  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a3ab  call    cs:__imp_GetModuleHandleA
0x18001a3b1  mov     r8, rdi
0x18001a3b4  mov     edx, 7F1h
0x18001a3b9  mov     rcx, rax
0x18001a3bc  call    _Intlstr_FormatString_FormatMessage
0x18001a3c1  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001a3c5  lea     r9, [rbp+EventDescriptor]
0x18001a3c9  mov     byte ptr [rbp+EventDescriptor.Keyword], r14b
0x18001a3cd  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001a3d4  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001a3d8  mov     r8d, r15d
0x18001a3db  mov     [rsp+60h+var_38], rsi; __int64
0x18001a3e0  mov     ecx, r13d; int
0x18001a3e3  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001a3e8  mov     [rsp+60h+var_40], rsi; __int64
0x18001a3ed  call    MI_ReportErrorDetails_ForCustomError
0x18001a3f2  cmp     cs:NITS_PRESENCE_STUB, r14
0x18001a3f9  jz      short loc_18001A44A
0x18001a3fb  mov     rax, cs:off_180047AB8
0x18001a402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a407  mov     [rbp+var_20], 0A9h
0x18001a40e  test    eax, eax
0x18001a410  mov     dword ptr [rsp+60h+var_40], esi
0x18001a414  lea     rax, aAdminWmiWinomi_7; "admin\\wmi\\winomi\\mp\\etw\\demux.c"
0x18001a41b  mov     qword ptr [rbp+EventDescriptor.Id], rsi
0x18001a41f  mov     ecx, esi
0x18001a421  mov     [rbp+EventDescriptor.Keyword], rax
0x18001a425  mov     rax, cs:off_180047A80
0x18001a42c  lea     r9, [rbp+EventDescriptor]
0x18001a430  lea     r8, aIgnoringErrorD; "Ignoring error deliberately"
0x18001a437  mov     [rbp+var_1C], r12d
0x18001a43b  lea     rdx, aNitsPresenceSt_0; "!((NITS_PRESENCE_STUB != NitsStubbedOut"...
0x18001a442  setz    cl
0x18001a445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a44a  mov     eax, 4
0x18001a44f  mov     rcx, [rbp+var_10]
0x18001a453  xor     rcx, rsp; StackCookie
0x18001a456  call    __security_check_cookie
0x18001a45b  mov     rbx, [rsp+60h+arg_10]
0x18001a463  add     rsp, 60h
0x18001a467  pop     r15
0x18001a469  pop     r14
0x18001a46b  pop     r13
0x18001a46d  pop     r12
0x18001a46f  pop     rdi
0x18001a470  pop     rsi
0x18001a471  pop     rbp
0x18001a472  retn
```
