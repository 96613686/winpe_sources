# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800c509c`
- end: `0x1800c5263`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `455`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800c4dac`
- `0x1800c509c`

## callees

- `0x18007dc50`
- `0x18008ead4`
- `0x1800c509c`
- `0x1800f0a90`
- `0x1800f2478`
- `0x18011c6c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c50c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c51dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c50c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c51dd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c50b3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c51d3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c50b3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800c51d3`

## string_xrefs

- `0x1800c5121`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800c51f8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800c5224`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  unsigned __int64 *v4; // r8
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rax
  wil *v8; // rax
  wil *v9; // rbx
  unsigned int v11; // edi
  const WCHAR *v12; // rax
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rcx
  int DirectoryDeepNoThrow; // eax
  const struct std::nothrow_t *v16; // rdx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  unsigned int v21; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int64 v23; // [rsp+48h] [rbp+10h] BYREF

  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 3 )
  {
    v23 = 0;
    if ( !wil::try_get_parent_path_range(this, (const unsigned __int16 *)&v23, v4) )
      goto LABEL_22;
    v5 = v23;
    v6 = v23 + 1;
    v7 = 2 * (v23 + 1);
    if ( !is_mul_ok(v23 + 1, 2u) )
      v7 = -1;
    v8 = (wil *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        v21);
      return 2147942414LL;
    }
    if ( v6 )
    {
      if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
      {
        v11 = -2147024809;
        *(_WORD *)v8 = 0;
      }
      else
      {
        v12 = this;
        v13 = (unsigned __int16 *)v9;
        do
        {
          if ( !v5 )
            break;
          if ( !*v12 )
            break;
          *v13++ = *v12++;
          --v5;
          --v6;
        }
        while ( v6 );
        v14 = v13 - 1;
        v11 = v6 == 0 ? 0x8007007A : 0;
        if ( v6 )
          v14 = v13;
        *v14 = 0;
        if ( v6 )
        {
          DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v9, v13);
          v11 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v17 = (unsigned int)DirectoryDeepNoThrow;
            v18 = 132;
LABEL_29:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v17,
              v21);
            operator delete(v9, v20);
            return v11;
          }
          operator delete(v9, v16);
LABEL_22:
          if ( !CreateDirectoryW(this, 0) )
          {
            LastError = GetLastError();
            if ( LastError != 183 )
            {
              if ( LastError )
              {
                v19 = 139;
                return wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)v19,
                         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                         (const char *)LastError,
                         v21);
              }
            }
          }
          return 0;
        }
      }
    }
    else
    {
      v11 = -2147024809;
    }
    v17 = v11;
    v18 = 131;
    goto LABEL_29;
  }
  if ( LastError != 183 && LastError )
  {
    v19 = 145;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v19,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
             (const char *)LastError,
             v21);
  }
  return 0;
}

```

## disassembly

```asm
0x1800c509c  mov     [rsp+arg_0], rbx
0x1800c50a1  mov     [rsp+arg_10], rbp
0x1800c50a6  push    rsi
0x1800c50a7  push    rdi
0x1800c50a8  push    r14; int
0x1800c50aa  sub     rsp, 20h
0x1800c50ae  xor     edx, edx; lpSecurityAttributes
0x1800c50b0  mov     rbp, rcx
0x1800c50b3  call    cs:__imp_CreateDirectoryW
0x1800c50b9  xor     r14d, r14d
0x1800c50bc  test    eax, eax
0x1800c50be  jnz     loc_1800C524E
0x1800c50c4  call    cs:__imp_GetLastError
0x1800c50ca  cmp     eax, 3
0x1800c50cd  jnz     loc_1800C523C
0x1800c50d3  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 *
0x1800c50d8  mov     [rsp+38h+arg_8], r14
0x1800c50dd  mov     rcx, rbp; lpStringSource
0x1800c50e0  call    ?try_get_parent_path_range@wil@@YA_NPEBGPEA_K@Z; wil::try_get_parent_path_range(ushort const *,unsigned __int64 *)
0x1800c50e5  test    al, al
0x1800c50e7  jz      loc_1800C51CE
0x1800c50ed  mov     rdi, [rsp+38h+arg_8]
0x1800c50f2  lea     rcx, [r14-1]
0x1800c50f6  lea     eax, [r14+2]
0x1800c50fa  lea     rsi, [rdi+1]
0x1800c50fe  mul     rsi
0x1800c5101  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c5108  cmovb   rax, rcx
0x1800c510c  mov     rcx, rax; unsigned __int64
0x1800c510f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c5114  mov     rbx, rax
0x1800c5117  test    rax, rax
0x1800c511a  jnz     short loc_1800C5141
0x1800c511c  mov     rcx, [rsp+38h]; this
0x1800c5121  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c5128  mov     ebx, 8007000Eh
0x1800c512d  mov     edx, 82h; void *
0x1800c5132  mov     r9d, ebx; char *
0x1800c5135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c513a  mov     eax, ebx
0x1800c513c  jmp     loc_1800C5250
0x1800c5141  test    rsi, rsi
0x1800c5144  jz      loc_1800C5209
0x1800c514a  cmp     rsi, 7FFFFFFFh
0x1800c5151  jbe     short loc_1800C515D
0x1800c5153  mov     edi, 80070057h
0x1800c5158  jmp     loc_1800C5213
0x1800c515d  cmp     rdi, 7FFFFFFEh
0x1800c5164  ja      short loc_1800C5153
0x1800c5166  mov     rax, rbp
0x1800c5169  mov     rdx, rbx
0x1800c516c  test    rdi, rdi
0x1800c516f  jz      short loc_1800C518D
0x1800c5171  movzx   ecx, word ptr [rax]
0x1800c5174  test    cx, cx
0x1800c5177  jz      short loc_1800C518D
0x1800c5179  mov     [rdx], cx
0x1800c517c  add     rax, 2
0x1800c5180  add     rdx, 2; unsigned __int16 *
0x1800c5184  dec     rdi
0x1800c5187  sub     rsi, 1
0x1800c518b  jnz     short loc_1800C516C
0x1800c518d  mov     rax, rsi
0x1800c5190  lea     rcx, [rdx-2]
0x1800c5194  neg     rax
0x1800c5197  sbb     edi, edi
0x1800c5199  not     edi
0x1800c519b  and     edi, 8007007Ah
0x1800c51a1  test    rsi, rsi
0x1800c51a4  cmovnz  rcx, rdx
0x1800c51a8  mov     [rcx], r14w
0x1800c51ac  jz      short loc_1800C5217
0x1800c51ae  mov     rcx, rbx; this
0x1800c51b1  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800c51b6  mov     edi, eax
0x1800c51b8  test    eax, eax
0x1800c51ba  jns     short loc_1800C51C6
0x1800c51bc  mov     r9d, eax
0x1800c51bf  mov     edx, 84h
0x1800c51c4  jmp     short loc_1800C521F
0x1800c51c6  mov     rcx, rbx; void *
0x1800c51c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c51ce  xor     edx, edx; lpSecurityAttributes
0x1800c51d0  mov     rcx, rbp; lpPathName
0x1800c51d3  call    cs:__imp_CreateDirectoryW
0x1800c51d9  test    eax, eax
0x1800c51db  jnz     short loc_1800C524E
0x1800c51dd  call    cs:__imp_GetLastError
0x1800c51e3  cmp     eax, 0B7h
0x1800c51e8  jz      short loc_1800C524E
0x1800c51ea  test    eax, eax
0x1800c51ec  jz      short loc_1800C524E
0x1800c51ee  mov     edx, 8Bh; void *
0x1800c51f3  mov     rcx, [rsp+38h]; this
0x1800c51f8  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c51ff  mov     r9d, eax; char *
0x1800c5202  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c5207  jmp     short loc_1800C5250
0x1800c5209  mov     edi, 80070057h
0x1800c520e  test    rsi, rsi
0x1800c5211  jz      short loc_1800C5217
0x1800c5213  mov     [rax], r14w
0x1800c5217  mov     r9d, edi; char *
0x1800c521a  mov     edx, 83h; void *
0x1800c521f  mov     rcx, [rsp+38h]; this
0x1800c5224  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c522b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5230  mov     rcx, rbx; void *
0x1800c5233  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c5238  mov     eax, edi
0x1800c523a  jmp     short loc_1800C5250
0x1800c523c  cmp     eax, 0B7h
0x1800c5241  jz      short loc_1800C524E
0x1800c5243  test    eax, eax
0x1800c5245  jz      short loc_1800C524E
0x1800c5247  mov     edx, 91h
0x1800c524c  jmp     short loc_1800C51F3
0x1800c524e  xor     eax, eax
0x1800c5250  mov     rbx, [rsp+38h+arg_0]
0x1800c5255  mov     rbp, [rsp+38h+arg_10]
0x1800c525a  add     rsp, 20h
0x1800c525e  pop     r14
0x1800c5260  pop     rdi
0x1800c5261  pop     rsi
0x1800c5262  retn
```
