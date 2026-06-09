# BaseCreateVDMEnvironment

- ea: `0x180043664`
- end: `0x180043bdb`
- name: `BaseCreateVDMEnvironment`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800643a0`

## callees

- `0x18000ccf0`
- `0x180028fe0`
- `0x180043664`
- `0x180061d70`
- `0x1800673c4`

## import_xrefs

- `ntdll!RtlCreateEnvironmentEx` at `0x180043ae0`
- `ntdll!RtlCreateEnvironmentEx` at `0x180043ae0`
- `ntdll!RtlDestroyEnvironment` at `0x180043b2c`
- `ntdll!RtlDestroyEnvironment` at `0x180043b65`
- `ntdll!RtlDestroyEnvironment` at `0x18008323f`
- `ntdll!RtlDestroyEnvironment` at `0x180043b2c`
- `ntdll!RtlDestroyEnvironment` at `0x180043b65`
- `ntdll!RtlDestroyEnvironment` at `0x18008323f`
- `ntdll!RtlCreateEnvironment` at `0x1800436bc`
- `ntdll!RtlCreateEnvironment` at `0x1800436bc`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180043b16`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180043b16`
- `ntdll!wcslen` at `0x1800437dc`
- `ntdll!wcslen` at `0x1800438fb`
- `ntdll!wcslen` at `0x1800437dc`
- `ntdll!wcslen` at `0x1800438fb`
- `ntdll!RtlSetLastWin32Error` at `0x180043bbc`
- `ntdll!RtlSetLastWin32Error` at `0x180043bbc`
- `ntdll!RtlFreeHeap` at `0x180043b88`
- `ntdll!RtlFreeHeap` at `0x180083264`
- `ntdll!RtlFreeHeap` at `0x180043b88`
- `ntdll!RtlFreeHeap` at `0x180083264`
- `ntdll!RtlAllocateHeap` at `0x180043752`
- `ntdll!RtlAllocateHeap` at `0x180043752`

## pseudocode

```c
__int64 __fastcall BaseCreateVDMEnvironment(wchar_t *a1, struct _STRING *a2, UNICODE_STRING *a3)
{
  UNICODE_STRING *v3; // rsi
  struct _STRING *v4; // r14
  wchar_t *v5; // rdi
  void *v6; // r12
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  wchar_t *v9; // rcx
  int i; // edx
  __int16 v11; // ax
  SIZE_T v12; // r8
  __int64 v13; // rcx
  PVOID Heap; // rax
  int v15; // r15d
  wchar_t *v16; // rbx
  WCHAR *v17; // rdi
  wchar_t v18; // ax
  wchar_t v19; // cx
  wchar_t v20; // cx
  _WORD *v21; // rdi
  int EnvNameType_U; // eax
  wchar_t *v23; // rcx
  wchar_t v24; // ax
  unsigned int v25; // r13d
  __int64 v26; // rsi
  DWORD ShortPathNameW; // eax
  unsigned int v28; // edx
  __int64 v29; // r14
  const WCHAR *v30; // r14
  __int64 v31; // rsi
  DWORD v32; // eax
  unsigned int v33; // edx
  WCHAR *v34; // rcx
  __int64 v35; // rsi
  DWORD v36; // eax
  unsigned int v37; // ecx
  int Environment; // eax
  NTSTATUS v39; // ebx
  wchar_t *String; // [rsp+38h] [rbp-50h] BYREF
  wchar_t *v42; // [rsp+40h] [rbp-48h]
  PVOID v43; // [rsp+48h] [rbp-40h]
  USHORT v47; // [rsp+A8h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  String = 0;
  v6 = 0;
  v43 = 0;
  if ( !a2 || (v7 = 0, !a3) )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  if ( a1 )
  {
    String = a1;
  }
  else
  {
    v8 = RtlCreateEnvironment(1u, &String);
    if ( v8 < 0 )
    {
      BaseSetLastNTError((unsigned int)v8);
      String = 0;
      goto LABEL_73;
    }
  }
  v9 = String;
  for ( i = 0; ; ++i )
  {
    v11 = *v9++;
    if ( !v11 && !*v9 )
      break;
  }
  v12 = 2LL * (unsigned int)(i + 262);
  if ( v12 <= 0xFFFF )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    v6 = Heap;
    v43 = Heap;
    if ( Heap )
    {
      v15 = 258;
      v16 = String;
      v17 = (WCHAR *)Heap;
      while ( 1 )
      {
        v18 = *v16;
        if ( !*v16 )
          break;
        if ( v18 == 61 )
        {
          v19 = v16[1];
          if ( (unsigned __int16)(v19 - 65) > 0x19u && (unsigned __int16)(v19 - 97) > 0x19u
            || v16[2] != 58
            || v16[3] != 61
            || wcslen(v16) < 7
            || !v16[7]
            && (v16[6] == 92 || v16[6] == 47)
            && v16[5] == 58
            && ((v20 = v16[4], (unsigned __int16)(v20 - 65) <= 0x19u) || (unsigned __int16)(v20 - 97) <= 0x19u) )
          {
            EnvNameType_U = 1;
          }
          else
          {
            *v17 = *v16;
            v21 = v17 + 1;
            *v21 = v16[1];
            v21[1] = v16[2];
            v21[2] = v16[3];
            v17 = v21 + 3;
            v16 += 4;
            EnvNameType_U = 2;
          }
        }
        else
        {
          v23 = v16;
          v42 = v16;
          while ( v18 )
          {
            *v17++ = v18;
            ++v16;
            if ( v18 == 61 )
              break;
            v18 = *v16;
          }
          EnvNameType_U = BaseGetEnvNameType_U(v23, (unsigned int)(v16 - v23) - 1);
        }
        if ( EnvNameType_U == 1 )
        {
          do
          {
            v24 = *v16;
            *v17++ = *v16++;
          }
          while ( v24 );
        }
        else if ( EnvNameType_U == 2 )
        {
          v25 = wcslen(v16);
          v26 = v25 + 1;
          ShortPathNameW = GetShortPathNameW(v16, v17, v26 + v15);
          v28 = ShortPathNameW;
          if ( ShortPathNameW && ShortPathNameW < (int)v26 + v15 )
          {
            v29 = (unsigned int)v26;
          }
          else
          {
            v29 = (unsigned int)v26;
            memmove_0(v17, v16, 2 * v26);
            v28 = v25;
          }
          v17 += v28 + 1;
          v16 += v29;
          if ( v28 > (unsigned int)v26 )
            v15 += v26 - v28;
        }
        else
        {
          v30 = v16;
          v42 = v16;
          while ( *v16 )
          {
            if ( *v16 == 59 )
            {
              v31 = v16 - v30;
              if ( (_DWORD)v31 )
              {
                *v16 = 0;
                v32 = GetShortPathNameW(v30, v17, v31 + v15 + 1);
                v33 = v32;
                if ( !v32 || v32 > (int)v31 + v15 )
                {
                  memmove_0(v17, v30, 2LL * (unsigned int)v31);
                  v33 = v16 - v30;
                }
                v34 = &v17[v33];
                *v16 = 59;
                *v34 = 59;
                v17 = v34 + 1;
                ++v16;
                if ( v33 > (unsigned int)v31 )
                  v15 += v31 - v33;
              }
              while ( *v16 == 59 )
              {
                *v17++ = 59;
                ++v16;
              }
              v30 = v16;
              v42 = v16;
            }
            else
            {
              ++v16;
            }
          }
          v35 = v16 - v30;
          if ( (_DWORD)v35 )
          {
            v36 = GetShortPathNameW(v30, v17, v35 + v15 + 1);
            v37 = v36;
            if ( !v36 || v36 > (unsigned int)v35 )
            {
              memmove_0(v17, v30, 2LL * (unsigned int)v35);
              v37 = v16 - v30;
            }
            v17 += v37;
            if ( v37 > (unsigned int)v35 )
              v15 += v35 - v37;
          }
          *v17++ = *v16++;
        }
      }
      *v17 = 0;
      v47 = (_WORD)v17 + 2 - (_WORD)v6;
      v3 = a3;
      a3->Length = v47;
      a3->MaximumLength = v47;
      Environment = RtlCreateEnvironmentEx(v6, &a3->Buffer, 0);
      if ( Environment >= 0 )
      {
        v4 = a2;
        v39 = RtlUnicodeStringToAnsiString(a2, a3, 1u);
        if ( v39 >= 0 )
        {
          v7 = 1;
        }
        else
        {
          RtlDestroyEnvironment(a3->Buffer);
          BaseSetLastNTError((unsigned int)v39);
          v7 = 0;
        }
      }
      else
      {
        BaseSetLastNTError((unsigned int)Environment);
        v7 = 0;
        v4 = a2;
      }
      v5 = a1;
      goto LABEL_73;
    }
    v13 = 3221225626LL;
  }
  else
  {
    v13 = 3221225473LL;
  }
  BaseSetLastNTError(v13);
LABEL_73:
  if ( !v5 && String )
    RtlDestroyEnvironment(String);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( !v7 )
  {
    *v3 = 0;
    *v4 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180043664  mov     rax, rsp
0x180043667  mov     [rax+18h], r8
0x18004366b  mov     [rax+10h], rdx
0x18004366f  mov     [rax+8], rcx
0x180043673  push    rbx
0x180043674  push    rsi
0x180043675  push    rdi
0x180043676  push    r12
0x180043678  push    r13
0x18004367a  push    r14
0x18004367c  push    r15
0x18004367e  sub     rsp, 50h
0x180043682  mov     rsi, r8
0x180043685  mov     r14, rdx
0x180043688  mov     rdi, rcx
0x18004368b  xor     r13d, r13d
0x18004368e  mov     [rax-50h], r13
0x180043692  mov     r12d, r13d
0x180043695  mov     [rax-40h], r13
0x180043699  test    rdx, rdx
0x18004369c  jz      loc_180043BB7
0x1800436a2  mov     ebx, r13d
0x1800436a5  mov     [rax-68h], ebx
0x1800436a8  test    r8, r8
0x1800436ab  jz      loc_180043BB7
0x1800436b1  test    rcx, rcx
0x1800436b4  jnz     short loc_1800436DD
0x1800436b6  lea     rdx, [rax-50h]; Environment
0x1800436ba  mov     cl, 1; Inherit
0x1800436bc  call    cs:__imp_RtlCreateEnvironment
0x1800436c3  nop     dword ptr [rax+rax+00h]
0x1800436c8  test    eax, eax
0x1800436ca  jns     short loc_1800436E2
0x1800436cc  mov     ecx, eax
0x1800436ce  call    BaseSetLastNTError
0x1800436d3  mov     [rsp+88h+String], r13
0x1800436d8  jmp     loc_180043B56
0x1800436dd  mov     [rsp+88h+String], rcx
0x1800436e2  mov     [rsp+88h+arg_18], r13d
0x1800436ea  mov     rcx, [rsp+88h+String]
0x1800436ef  mov     [rsp+88h+var_60], rcx
0x1800436f4  mov     edx, r13d
0x1800436f7  movzx   eax, word ptr [rcx]
0x1800436fa  add     rcx, 2
0x1800436fe  mov     [rsp+88h+var_60], rcx
0x180043703  test    ax, ax
0x180043706  jnz     loc_180043BA9
0x18004370c  cmp     [rcx], r13w
0x180043710  jnz     loc_180043BA9
0x180043716  lea     eax, [rdx+2]
0x180043719  mov     [rsp+88h+arg_18], eax
0x180043720  add     eax, 104h
0x180043725  mov     r8d, eax
0x180043728  add     r8, r8; Size
0x18004372b  cmp     r8, 0FFFFh
0x180043732  jbe     short loc_180043743
0x180043734  mov     ecx, 0C0000001h
0x180043739  call    BaseSetLastNTError
0x18004373e  jmp     loc_180043B56
0x180043743  mov     rcx, gs:60h
0x18004374c  xor     edx, edx; Flags
0x18004374e  mov     rcx, [rcx+30h]; HeapHandle
0x180043752  call    cs:__imp_RtlAllocateHeap
0x180043759  nop     dword ptr [rax+rax+00h]
0x18004375e  mov     r12, rax
0x180043761  mov     [rsp+88h+var_40], rax
0x180043766  test    rax, rax
0x180043769  jnz     short loc_180043772
0x18004376b  mov     ecx, 0C000009Ah
0x180043770  jmp     short loc_180043739
0x180043772  mov     r15d, 102h
0x180043778  mov     [rsp+88h+var_64], r15d
0x18004377d  mov     rbx, [rsp+88h+String]
0x180043782  mov     [rsp+88h+var_60], rbx
0x180043787  mov     rdi, r12
0x18004378a  mov     [rsp+88h+var_58], r12
0x18004378f  movzx   eax, word ptr [rbx]
0x180043792  test    ax, ax
0x180043795  jz      loc_180043AB0
0x18004379b  cmp     ax, 3Dh ; '='
0x18004379f  jnz     loc_180043892
0x1800437a5  lea     rsi, [rbx+2]
0x1800437a9  movzx   ecx, word ptr [rsi]
0x1800437ac  lea     eax, [rcx-41h]
0x1800437af  cmp     ax, 19h
0x1800437b3  jbe     short loc_1800437C3
0x1800437b5  sub     cx, 61h ; 'a'
0x1800437b9  cmp     cx, 19h
0x1800437bd  ja      loc_18004388B
0x1800437c3  cmp     word ptr [rbx+4], 3Ah ; ':'
0x1800437c8  jnz     loc_18004388B
0x1800437ce  cmp     word ptr [rbx+6], 3Dh ; '='
0x1800437d3  jnz     loc_18004388B
0x1800437d9  mov     rcx, rbx; String
0x1800437dc  call    cs:__imp_wcslen
0x1800437e3  nop     dword ptr [rax+rax+00h]
0x1800437e8  cmp     rax, 7
0x1800437ec  jb      loc_18004388B
0x1800437f2  cmp     [rbx+0Eh], r13w
0x1800437f7  jnz     short loc_180043825
0x1800437f9  cmp     word ptr [rbx+0Ch], 5Ch ; '\'
0x1800437fe  jz      short loc_180043807
0x180043800  cmp     word ptr [rbx+0Ch], 2Fh ; '/'
0x180043805  jnz     short loc_180043825
0x180043807  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x18004380c  jnz     short loc_180043825
0x18004380e  movzx   ecx, word ptr [rbx+8]
0x180043812  lea     eax, [rcx-41h]
0x180043815  cmp     ax, 19h
0x180043819  jbe     short loc_18004388B
0x18004381b  sub     cx, 61h ; 'a'
0x18004381f  cmp     cx, 19h
0x180043823  jbe     short loc_18004388B
0x180043825  movzx   eax, word ptr [rbx]
0x180043828  mov     [rdi], ax
0x18004382b  add     rdi, 2
0x18004382f  mov     [rsp+88h+var_58], rdi
0x180043834  mov     rbx, rsi
0x180043837  mov     [rsp+88h+var_60], rbx
0x18004383c  movzx   eax, word ptr [rsi]
0x18004383f  mov     [rdi], ax
0x180043842  lea     rcx, [rdi+2]
0x180043846  mov     [rsp+88h+var_58], rcx
0x18004384b  add     rbx, 2
0x18004384f  mov     [rsp+88h+var_60], rbx
0x180043854  movzx   eax, word ptr [rbx]
0x180043857  mov     [rcx], ax
0x18004385a  add     rcx, 2
0x18004385e  mov     [rsp+88h+var_58], rcx
0x180043863  add     rbx, 2
0x180043867  mov     [rsp+88h+var_60], rbx
0x18004386c  movzx   eax, word ptr [rbx]
0x18004386f  mov     [rcx], ax
0x180043872  lea     rdi, [rcx+2]
0x180043876  mov     [rsp+88h+var_58], rdi
0x18004387b  add     rbx, 2
0x18004387f  mov     [rsp+88h+var_60], rbx
0x180043884  mov     eax, 2
0x180043889  jmp     short loc_1800438CF
0x18004388b  mov     eax, 1
0x180043890  jmp     short loc_1800438CF
0x180043892  mov     rcx, rbx; String2
0x180043895  mov     [rsp+88h+var_48], rbx
0x18004389a  test    ax, ax
0x18004389d  jz      short loc_1800438BF
0x18004389f  mov     [rdi], ax
0x1800438a2  add     rdi, 2
0x1800438a6  mov     [rsp+88h+var_58], rdi
0x1800438ab  add     rbx, 2
0x1800438af  mov     [rsp+88h+var_60], rbx
0x1800438b4  cmp     ax, 3Dh ; '='
0x1800438b8  jz      short loc_1800438BF
0x1800438ba  movzx   eax, word ptr [rbx]
0x1800438bd  jmp     short loc_18004389A
0x1800438bf  mov     rdx, rbx
0x1800438c2  sub     rdx, rcx
0x1800438c5  sar     rdx, 1
0x1800438c8  dec     edx; MaxCount
0x1800438ca  call    BaseGetEnvNameType_U
0x1800438cf  cmp     eax, 1
0x1800438d2  jnz     short loc_1800438F3
0x1800438d4  movzx   eax, word ptr [rbx]
0x1800438d7  mov     [rdi], ax
0x1800438da  add     rdi, 2
0x1800438de  mov     [rsp+88h+var_58], rdi
0x1800438e3  add     rbx, 2
0x1800438e7  mov     [rsp+88h+var_60], rbx
0x1800438ec  test    ax, ax
0x1800438ef  jz      short loc_18004396A
0x1800438f1  jmp     short loc_1800438D4
0x1800438f3  cmp     eax, 2
0x1800438f6  jnz     short loc_18004396F
0x1800438f8  mov     rcx, rbx; String
0x1800438fb  call    cs:__imp_wcslen
0x180043902  nop     dword ptr [rax+rax+00h]
0x180043907  mov     r13, rax
0x18004390a  lea     esi, [rax+1]
0x18004390d  lea     r14d, [rsi+r15]
0x180043911  mov     r8d, r14d; cchBuffer
0x180043914  mov     rdx, rdi; lpszShortPath
0x180043917  mov     rcx, rbx; lpszLongPath
0x18004391a  call    GetShortPathNameW
0x18004391f  mov     edx, eax
0x180043921  test    eax, eax
0x180043923  jz      short loc_18004392F
0x180043925  cmp     eax, r14d
0x180043928  jnb     short loc_18004392F
0x18004392a  mov     r14d, esi
0x18004392d  jmp     short loc_180043944
0x18004392f  mov     r14d, esi
0x180043932  lea     r8, [rsi+rsi]; Size
0x180043936  mov     rdx, rbx; Src
0x180043939  mov     rcx, rdi; void *
0x18004393c  call    memmove_0
0x180043941  mov     edx, r13d
0x180043944  lea     eax, [rdx+1]
0x180043947  lea     rdi, [rdi+rax*2]
0x18004394b  mov     [rsp+88h+var_58], rdi
0x180043950  lea     rbx, [rbx+r14*2]
0x180043954  mov     [rsp+88h+var_60], rbx
0x180043959  cmp     edx, esi
0x18004395b  jbe     short loc_180043967
0x18004395d  sub     esi, edx
0x18004395f  add     r15d, esi
0x180043962  mov     [rsp+88h+var_64], r15d
0x180043967  xor     r13d, r13d
0x18004396a  jmp     loc_18004378F
0x18004396f  mov     r14, rbx
0x180043972  mov     [rsp+88h+var_48], rbx
0x180043977  mov     eax, 3Bh ; ';'
0x18004397c  cmp     [rbx], r13w
0x180043980  jz      loc_180043A3E
0x180043986  cmp     [rbx], ax
0x180043989  jnz     loc_180043A30
0x18004398f  mov     rsi, rbx
0x180043992  sub     rsi, r14
0x180043995  sar     rsi, 1
0x180043998  test    esi, esi
0x18004399a  jz      short loc_180043A0A
0x18004399c  mov     [rbx], r13w
0x1800439a0  lea     r13d, [rsi+r15]
0x1800439a4  lea     r8d, [r13+1]; cchBuffer
0x1800439a8  mov     rdx, rdi; lpszShortPath
0x1800439ab  mov     rcx, r14; lpszLongPath
0x1800439ae  call    GetShortPathNameW
0x1800439b3  mov     edx, eax
0x1800439b5  test    eax, eax
0x1800439b7  jz      short loc_1800439BE
0x1800439b9  cmp     eax, r13d
0x1800439bc  jbe     short loc_1800439D1
0x1800439be  mov     r8d, esi
0x1800439c1  add     r8, r8; Size
0x1800439c4  mov     rdx, r14; Src
0x1800439c7  mov     rcx, rdi; void *
0x1800439ca  call    memmove_0
0x1800439cf  mov     edx, esi
0x1800439d1  mov     eax, edx
0x1800439d3  lea     rcx, [rdi+rax*2]
0x1800439d7  mov     [rsp+88h+var_58], rcx
0x1800439dc  mov     eax, 3Bh ; ';'
0x1800439e1  mov     [rbx], ax
0x1800439e4  mov     [rcx], ax
0x1800439e7  lea     rdi, [rcx+2]
0x1800439eb  mov     [rsp+88h+var_58], rdi
0x1800439f0  add     rbx, 2
0x1800439f4  mov     [rsp+88h+var_60], rbx
0x1800439f9  cmp     edx, esi
0x1800439fb  jbe     short loc_180043A07
0x1800439fd  sub     esi, edx
0x1800439ff  add     r15d, esi
0x180043a02  mov     [rsp+88h+var_64], r15d
0x180043a07  xor     r13d, r13d
0x180043a0a  cmp     [rbx], ax
0x180043a0d  jnz     short loc_180043A26
0x180043a0f  mov     [rdi], ax
0x180043a12  add     rdi, 2
0x180043a16  mov     [rsp+88h+var_58], rdi
0x180043a1b  add     rbx, 2
0x180043a1f  mov     [rsp+88h+var_60], rbx
0x180043a24  jmp     short loc_180043A0A
0x180043a26  mov     r14, rbx
0x180043a29  mov     [rsp+88h+var_48], rbx
0x180043a2e  jmp     short loc_180043A39
0x180043a30  add     rbx, 2
0x180043a34  mov     [rsp+88h+var_60], rbx
0x180043a39  jmp     loc_18004397C
0x180043a3e  mov     rsi, rbx
0x180043a41  sub     rsi, r14
0x180043a44  sar     rsi, 1
0x180043a47  test    esi, esi
0x180043a49  jz      short loc_180043A93
0x180043a4b  lea     r8d, [r15+1]
0x180043a4f  add     r8d, esi; cchBuffer
0x180043a52  mov     rdx, rdi; lpszShortPath
0x180043a55  mov     rcx, r14; lpszLongPath
0x180043a58  call    GetShortPathNameW
0x180043a5d  mov     ecx, eax
0x180043a5f  test    eax, eax
0x180043a61  jz      short loc_180043A67
0x180043a63  cmp     eax, esi
0x180043a65  jbe     short loc_180043A7A
0x180043a67  mov     r8d, esi
0x180043a6a  add     r8, r8; Size
0x180043a6d  mov     rdx, r14; Src
0x180043a70  mov     rcx, rdi; void *
0x180043a73  call    memmove_0
0x180043a78  mov     ecx, esi
0x180043a7a  mov     eax, ecx
0x180043a7c  lea     rdi, [rdi+rax*2]
0x180043a80  mov     [rsp+88h+var_58], rdi
0x180043a85  cmp     ecx, esi
0x180043a87  jbe     short loc_180043A93
0x180043a89  sub     esi, ecx
0x180043a8b  add     r15d, esi
0x180043a8e  mov     [rsp+88h+var_64], r15d
0x180043a93  movzx   eax, word ptr [rbx]
0x180043a96  mov     [rdi], ax
0x180043a99  add     rdi, 2
0x180043a9d  mov     [rsp+88h+var_58], rdi
0x180043aa2  add     rbx, 2
  ... truncated ...
```
