# BaseCreateVDMEnvironment

- ea: `0x18003fb7c`
- end: `0x1800400b6`
- name: `BaseCreateVDMEnvironment`
- size: `1338`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005e780`

## callees

- `0x18000c110`
- `0x18000f920`
- `0x18003fb7c`
- `0x18005c390`
- `0x180060b48`

## import_xrefs

- `ntdll!RtlCreateEnvironmentEx` at `0x18003ffe0`
- `ntdll!RtlCreateEnvironmentEx` at `0x18003ffe0`
- `ntdll!RtlDestroyEnvironment` at `0x180040020`
- `ntdll!RtlDestroyEnvironment` at `0x180040053`
- `ntdll!RtlDestroyEnvironment` at `0x18007b1c9`
- `ntdll!RtlDestroyEnvironment` at `0x180040020`
- `ntdll!RtlDestroyEnvironment` at `0x180040053`
- `ntdll!RtlDestroyEnvironment` at `0x18007b1c9`
- `ntdll!RtlCreateEnvironment` at `0x18003fbd4`
- `ntdll!RtlCreateEnvironment` at `0x18003fbd4`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180040010`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180040010`
- `ntdll!wcslen` at `0x18003fce8`
- `ntdll!wcslen` at `0x18003fe01`
- `ntdll!wcslen` at `0x18003fce8`
- `ntdll!wcslen` at `0x18003fe01`
- `ntdll!RtlSetLastWin32Error` at `0x18004009e`
- `ntdll!RtlSetLastWin32Error` at `0x18004009e`
- `ntdll!RtlFreeHeap` at `0x180040070`
- `ntdll!RtlFreeHeap` at `0x18007b1e8`
- `ntdll!RtlFreeHeap` at `0x180040070`
- `ntdll!RtlFreeHeap` at `0x18007b1e8`
- `ntdll!RtlAllocateHeap` at `0x18003fc64`
- `ntdll!RtlAllocateHeap` at `0x18003fc64`

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
0x18003fb7c  mov     rax, rsp
0x18003fb7f  mov     [rax+18h], r8
0x18003fb83  mov     [rax+10h], rdx
0x18003fb87  mov     [rax+8], rcx
0x18003fb8b  push    rbx
0x18003fb8c  push    rsi
0x18003fb8d  push    rdi
0x18003fb8e  push    r12
0x18003fb90  push    r13
0x18003fb92  push    r14
0x18003fb94  push    r15
0x18003fb96  sub     rsp, 50h
0x18003fb9a  mov     rsi, r8
0x18003fb9d  mov     r14, rdx
0x18003fba0  mov     rdi, rcx
0x18003fba3  xor     r13d, r13d
0x18003fba6  mov     [rax-50h], r13
0x18003fbaa  mov     r12d, r13d
0x18003fbad  mov     [rax-40h], r13
0x18003fbb1  test    rdx, rdx
0x18003fbb4  jz      loc_180040099
0x18003fbba  mov     ebx, r13d
0x18003fbbd  mov     [rax-68h], ebx
0x18003fbc0  test    r8, r8
0x18003fbc3  jz      loc_180040099
0x18003fbc9  test    rcx, rcx
0x18003fbcc  jnz     short loc_18003FBEF
0x18003fbce  lea     rdx, [rax-50h]; Environment
0x18003fbd2  mov     cl, 1; Inherit
0x18003fbd4  call    cs:__imp_RtlCreateEnvironment
0x18003fbda  test    eax, eax
0x18003fbdc  jns     short loc_18003FBF4
0x18003fbde  mov     ecx, eax
0x18003fbe0  call    BaseSetLastNTError
0x18003fbe5  mov     [rsp+88h+String], r13
0x18003fbea  jmp     loc_180040044
0x18003fbef  mov     [rsp+88h+String], rcx
0x18003fbf4  mov     [rsp+88h+arg_18], r13d
0x18003fbfc  mov     rcx, [rsp+88h+String]
0x18003fc01  mov     [rsp+88h+var_60], rcx
0x18003fc06  mov     edx, r13d
0x18003fc09  movzx   eax, word ptr [rcx]
0x18003fc0c  add     rcx, 2
0x18003fc10  mov     [rsp+88h+var_60], rcx
0x18003fc15  test    ax, ax
0x18003fc18  jnz     loc_18004008B
0x18003fc1e  cmp     [rcx], r13w
0x18003fc22  jnz     loc_18004008B
0x18003fc28  lea     eax, [rdx+2]
0x18003fc2b  mov     [rsp+88h+arg_18], eax
0x18003fc32  add     eax, 104h
0x18003fc37  mov     r8d, eax
0x18003fc3a  add     r8, r8; Size
0x18003fc3d  cmp     r8, 0FFFFh
0x18003fc44  jbe     short loc_18003FC55
0x18003fc46  mov     ecx, 0C0000001h
0x18003fc4b  call    BaseSetLastNTError
0x18003fc50  jmp     loc_180040044
0x18003fc55  mov     rcx, gs:60h
0x18003fc5e  xor     edx, edx; Flags
0x18003fc60  mov     rcx, [rcx+30h]; HeapHandle
0x18003fc64  call    cs:__imp_RtlAllocateHeap
0x18003fc6a  mov     r12, rax
0x18003fc6d  mov     [rsp+88h+var_40], rax
0x18003fc72  test    rax, rax
0x18003fc75  jnz     short loc_18003FC7E
0x18003fc77  mov     ecx, 0C000009Ah
0x18003fc7c  jmp     short loc_18003FC4B
0x18003fc7e  mov     r15d, 102h
0x18003fc84  mov     [rsp+88h+var_64], r15d
0x18003fc89  mov     rbx, [rsp+88h+String]
0x18003fc8e  mov     [rsp+88h+var_60], rbx
0x18003fc93  mov     rdi, r12
0x18003fc96  mov     [rsp+88h+var_58], r12
0x18003fc9b  movzx   eax, word ptr [rbx]
0x18003fc9e  test    ax, ax
0x18003fca1  jz      loc_18003FFB0
0x18003fca7  cmp     ax, 3Dh ; '='
0x18003fcab  jnz     loc_18003FD98
0x18003fcb1  lea     rsi, [rbx+2]
0x18003fcb5  movzx   ecx, word ptr [rsi]
0x18003fcb8  lea     eax, [rcx-41h]
0x18003fcbb  cmp     ax, 19h
0x18003fcbf  jbe     short loc_18003FCCF
0x18003fcc1  sub     cx, 61h ; 'a'
0x18003fcc5  cmp     cx, 19h
0x18003fcc9  ja      loc_18003FD91
0x18003fccf  cmp     word ptr [rbx+4], 3Ah ; ':'
0x18003fcd4  jnz     loc_18003FD91
0x18003fcda  cmp     word ptr [rbx+6], 3Dh ; '='
0x18003fcdf  jnz     loc_18003FD91
0x18003fce5  mov     rcx, rbx; String
0x18003fce8  call    cs:__imp_wcslen
0x18003fcee  cmp     rax, 7
0x18003fcf2  jb      loc_18003FD91
0x18003fcf8  cmp     [rbx+0Eh], r13w
0x18003fcfd  jnz     short loc_18003FD2B
0x18003fcff  cmp     word ptr [rbx+0Ch], 5Ch ; '\'
0x18003fd04  jz      short loc_18003FD0D
0x18003fd06  cmp     word ptr [rbx+0Ch], 2Fh ; '/'
0x18003fd0b  jnz     short loc_18003FD2B
0x18003fd0d  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x18003fd12  jnz     short loc_18003FD2B
0x18003fd14  movzx   ecx, word ptr [rbx+8]
0x18003fd18  lea     eax, [rcx-41h]
0x18003fd1b  cmp     ax, 19h
0x18003fd1f  jbe     short loc_18003FD91
0x18003fd21  sub     cx, 61h ; 'a'
0x18003fd25  cmp     cx, 19h
0x18003fd29  jbe     short loc_18003FD91
0x18003fd2b  movzx   eax, word ptr [rbx]
0x18003fd2e  mov     [rdi], ax
0x18003fd31  add     rdi, 2
0x18003fd35  mov     [rsp+88h+var_58], rdi
0x18003fd3a  mov     rbx, rsi
0x18003fd3d  mov     [rsp+88h+var_60], rbx
0x18003fd42  movzx   eax, word ptr [rsi]
0x18003fd45  mov     [rdi], ax
0x18003fd48  lea     rcx, [rdi+2]
0x18003fd4c  mov     [rsp+88h+var_58], rcx
0x18003fd51  add     rbx, 2
0x18003fd55  mov     [rsp+88h+var_60], rbx
0x18003fd5a  movzx   eax, word ptr [rbx]
0x18003fd5d  mov     [rcx], ax
0x18003fd60  add     rcx, 2
0x18003fd64  mov     [rsp+88h+var_58], rcx
0x18003fd69  add     rbx, 2
0x18003fd6d  mov     [rsp+88h+var_60], rbx
0x18003fd72  movzx   eax, word ptr [rbx]
0x18003fd75  mov     [rcx], ax
0x18003fd78  lea     rdi, [rcx+2]
0x18003fd7c  mov     [rsp+88h+var_58], rdi
0x18003fd81  add     rbx, 2
0x18003fd85  mov     [rsp+88h+var_60], rbx
0x18003fd8a  mov     eax, 2
0x18003fd8f  jmp     short loc_18003FDD5
0x18003fd91  mov     eax, 1
0x18003fd96  jmp     short loc_18003FDD5
0x18003fd98  mov     rcx, rbx; String2
0x18003fd9b  mov     [rsp+88h+var_48], rbx
0x18003fda0  test    ax, ax
0x18003fda3  jz      short loc_18003FDC5
0x18003fda5  mov     [rdi], ax
0x18003fda8  add     rdi, 2
0x18003fdac  mov     [rsp+88h+var_58], rdi
0x18003fdb1  add     rbx, 2
0x18003fdb5  mov     [rsp+88h+var_60], rbx
0x18003fdba  cmp     ax, 3Dh ; '='
0x18003fdbe  jz      short loc_18003FDC5
0x18003fdc0  movzx   eax, word ptr [rbx]
0x18003fdc3  jmp     short loc_18003FDA0
0x18003fdc5  mov     rdx, rbx
0x18003fdc8  sub     rdx, rcx
0x18003fdcb  sar     rdx, 1
0x18003fdce  dec     edx; MaxCount
0x18003fdd0  call    BaseGetEnvNameType_U
0x18003fdd5  cmp     eax, 1
0x18003fdd8  jnz     short loc_18003FDF9
0x18003fdda  movzx   eax, word ptr [rbx]
0x18003fddd  mov     [rdi], ax
0x18003fde0  add     rdi, 2
0x18003fde4  mov     [rsp+88h+var_58], rdi
0x18003fde9  add     rbx, 2
0x18003fded  mov     [rsp+88h+var_60], rbx
0x18003fdf2  test    ax, ax
0x18003fdf5  jz      short loc_18003FE6A
0x18003fdf7  jmp     short loc_18003FDDA
0x18003fdf9  cmp     eax, 2
0x18003fdfc  jnz     short loc_18003FE6F
0x18003fdfe  mov     rcx, rbx; String
0x18003fe01  call    cs:__imp_wcslen
0x18003fe07  mov     r13, rax
0x18003fe0a  lea     esi, [rax+1]
0x18003fe0d  lea     r14d, [rsi+r15]
0x18003fe11  mov     r8d, r14d; cchBuffer
0x18003fe14  mov     rdx, rdi; lpszShortPath
0x18003fe17  mov     rcx, rbx; lpszLongPath
0x18003fe1a  call    GetShortPathNameW
0x18003fe1f  mov     edx, eax
0x18003fe21  test    eax, eax
0x18003fe23  jz      short loc_18003FE2F
0x18003fe25  cmp     eax, r14d
0x18003fe28  jnb     short loc_18003FE2F
0x18003fe2a  mov     r14d, esi
0x18003fe2d  jmp     short loc_18003FE44
0x18003fe2f  mov     r14d, esi
0x18003fe32  lea     r8, [rsi+rsi]; Size
0x18003fe36  mov     rdx, rbx; Src
0x18003fe39  mov     rcx, rdi; void *
0x18003fe3c  call    memmove_0
0x18003fe41  mov     edx, r13d
0x18003fe44  lea     eax, [rdx+1]
0x18003fe47  lea     rdi, [rdi+rax*2]
0x18003fe4b  mov     [rsp+88h+var_58], rdi
0x18003fe50  lea     rbx, [rbx+r14*2]
0x18003fe54  mov     [rsp+88h+var_60], rbx
0x18003fe59  cmp     edx, esi
0x18003fe5b  jbe     short loc_18003FE67
0x18003fe5d  sub     esi, edx
0x18003fe5f  add     r15d, esi
0x18003fe62  mov     [rsp+88h+var_64], r15d
0x18003fe67  xor     r13d, r13d
0x18003fe6a  jmp     loc_18003FC9B
0x18003fe6f  mov     r14, rbx
0x18003fe72  mov     [rsp+88h+var_48], rbx
0x18003fe77  mov     eax, 3Bh ; ';'
0x18003fe7c  cmp     [rbx], r13w
0x18003fe80  jz      loc_18003FF3E
0x18003fe86  cmp     [rbx], ax
0x18003fe89  jnz     loc_18003FF30
0x18003fe8f  mov     rsi, rbx
0x18003fe92  sub     rsi, r14
0x18003fe95  sar     rsi, 1
0x18003fe98  test    esi, esi
0x18003fe9a  jz      short loc_18003FF0A
0x18003fe9c  mov     [rbx], r13w
0x18003fea0  lea     r13d, [rsi+r15]
0x18003fea4  lea     r8d, [r13+1]; cchBuffer
0x18003fea8  mov     rdx, rdi; lpszShortPath
0x18003feab  mov     rcx, r14; lpszLongPath
0x18003feae  call    GetShortPathNameW
0x18003feb3  mov     edx, eax
0x18003feb5  test    eax, eax
0x18003feb7  jz      short loc_18003FEBE
0x18003feb9  cmp     eax, r13d
0x18003febc  jbe     short loc_18003FED1
0x18003febe  mov     r8d, esi
0x18003fec1  add     r8, r8; Size
0x18003fec4  mov     rdx, r14; Src
0x18003fec7  mov     rcx, rdi; void *
0x18003feca  call    memmove_0
0x18003fecf  mov     edx, esi
0x18003fed1  mov     eax, edx
0x18003fed3  lea     rcx, [rdi+rax*2]
0x18003fed7  mov     [rsp+88h+var_58], rcx
0x18003fedc  mov     eax, 3Bh ; ';'
0x18003fee1  mov     [rbx], ax
0x18003fee4  mov     [rcx], ax
0x18003fee7  lea     rdi, [rcx+2]
0x18003feeb  mov     [rsp+88h+var_58], rdi
0x18003fef0  add     rbx, 2
0x18003fef4  mov     [rsp+88h+var_60], rbx
0x18003fef9  cmp     edx, esi
0x18003fefb  jbe     short loc_18003FF07
0x18003fefd  sub     esi, edx
0x18003feff  add     r15d, esi
0x18003ff02  mov     [rsp+88h+var_64], r15d
0x18003ff07  xor     r13d, r13d
0x18003ff0a  cmp     [rbx], ax
0x18003ff0d  jnz     short loc_18003FF26
0x18003ff0f  mov     [rdi], ax
0x18003ff12  add     rdi, 2
0x18003ff16  mov     [rsp+88h+var_58], rdi
0x18003ff1b  add     rbx, 2
0x18003ff1f  mov     [rsp+88h+var_60], rbx
0x18003ff24  jmp     short loc_18003FF0A
0x18003ff26  mov     r14, rbx
0x18003ff29  mov     [rsp+88h+var_48], rbx
0x18003ff2e  jmp     short loc_18003FF39
0x18003ff30  add     rbx, 2
0x18003ff34  mov     [rsp+88h+var_60], rbx
0x18003ff39  jmp     loc_18003FE7C
0x18003ff3e  mov     rsi, rbx
0x18003ff41  sub     rsi, r14
0x18003ff44  sar     rsi, 1
0x18003ff47  test    esi, esi
0x18003ff49  jz      short loc_18003FF93
0x18003ff4b  lea     r8d, [r15+1]
0x18003ff4f  add     r8d, esi; cchBuffer
0x18003ff52  mov     rdx, rdi; lpszShortPath
0x18003ff55  mov     rcx, r14; lpszLongPath
0x18003ff58  call    GetShortPathNameW
0x18003ff5d  mov     ecx, eax
0x18003ff5f  test    eax, eax
0x18003ff61  jz      short loc_18003FF67
0x18003ff63  cmp     eax, esi
0x18003ff65  jbe     short loc_18003FF7A
0x18003ff67  mov     r8d, esi
0x18003ff6a  add     r8, r8; Size
0x18003ff6d  mov     rdx, r14; Src
0x18003ff70  mov     rcx, rdi; void *
0x18003ff73  call    memmove_0
0x18003ff78  mov     ecx, esi
0x18003ff7a  mov     eax, ecx
0x18003ff7c  lea     rdi, [rdi+rax*2]
0x18003ff80  mov     [rsp+88h+var_58], rdi
0x18003ff85  cmp     ecx, esi
0x18003ff87  jbe     short loc_18003FF93
0x18003ff89  sub     esi, ecx
0x18003ff8b  add     r15d, esi
0x18003ff8e  mov     [rsp+88h+var_64], r15d
0x18003ff93  movzx   eax, word ptr [rbx]
0x18003ff96  mov     [rdi], ax
0x18003ff99  add     rdi, 2
0x18003ff9d  mov     [rsp+88h+var_58], rdi
0x18003ffa2  add     rbx, 2
0x18003ffa6  mov     [rsp+88h+var_60], rbx
0x18003ffab  jmp     loc_18003FE6A
0x18003ffb0  mov     [rdi], r13w
0x18003ffb4  add     rdi, 2
  ... truncated ...
```
