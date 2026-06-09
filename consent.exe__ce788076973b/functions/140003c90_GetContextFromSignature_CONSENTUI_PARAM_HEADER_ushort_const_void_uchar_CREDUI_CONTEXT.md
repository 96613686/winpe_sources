# GetContextFromSignature(_CONSENTUI_PARAM_HEADER *,ushort const *,void *,uchar *,_CREDUI_CONTEXT *)

- ea: `0x140003c90`
- end: `0x140003e2c`
- name: `?GetContextFromSignature@@YAJPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAXPEAEPEAU_CREDUI_CONTEXT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct _CONSENTUI_PARAM_HEADER *, const unsigned __int16 *, __int64, unsigned __int8 *, struct _CREDUI_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140003040`

## callees

- `0x140003c90`
- `0x140003e40`
- `0x140019534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003d1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003d1b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003cf5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003cf5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140003df7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140003df7`
- `SHLWAPI!SHStrDupW` at `0x140003cd7`
- `SHLWAPI!SHStrDupW` at `0x140003cd7`
- `SHLWAPI!PathUnquoteSpacesW` at `0x140003ceb`
- `SHLWAPI!PathUnquoteSpacesW` at `0x140003ceb`

## pseudocode

```c
__int64 __fastcall GetContextFromSignature(
        struct _CONSENTUI_PARAM_HEADER *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        struct _CREDUI_CONTEXT *a5)
{
  struct _CREDUI_CONTEXT *v5; // r15
  int v8; // esi
  int BinarySignature; // ebx
  signed int LastError; // eax
  const wchar_t *v13; // rax
  int v14; // r8d
  LPWSTR lpsz; // [rsp+80h] [rbp+8h] BYREF

  v5 = a5;
  v8 = 0;
  *a4 = 0;
  if ( (*((_BYTE *)a1 + 48) & 0x20) != 0 )
  {
    *(_DWORD *)v5 = 1;
    BinarySignature = 0;
  }
  else
  {
    lpsz = 0;
    BinarySignature = SHStrDupW(a2, &lpsz);
    if ( BinarySignature >= 0 )
    {
      PathUnquoteSpacesW(lpsz);
      if ( ImpersonateLoggedOnUser(*((HANDLE *)a1 + 3)) )
      {
        v14 = *((_DWORD *)a1 + 12);
        if ( (v14 & 1) == 0 || (v14 & 0x400) != 0 )
          v8 = 4096;
        BinarySignature = CuiGetBinarySignature(
                            (__int64)lpsz,
                            a3,
                            v14 & 0x40,
                            (unsigned int)(*((_DWORD *)a1 + 1) - 1) <= 1,
                            v8,
                            (int *)v5,
                            a4,
                            (LPWSTR *)v5 + 3,
                            (LPWSTR *)v5 + 2,
                            (PCCERT_CONTEXT *)v5 + 8,
                            (void **)v5 + 9);
        RevertToSelf();
      }
      else
      {
        LastError = GetLastError();
        BinarySignature = LastError;
        if ( LastError > 0 )
          BinarySignature = (unsigned __int16)LastError | 0x80070000;
      }
      CoTaskMemFree(lpsz);
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v13 = L"TRUE";
    if ( !*a4 )
      v13 = L"FALSE";
    WPP_SF_DdS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, a3, BinarySignature, *(_DWORD *)v5, (__int64)v13);
  }
  return (unsigned int)BinarySignature;
}

```

## disassembly

```asm
0x140003c90  mov     r11, rsp
0x140003c93  push    rbx
0x140003c94  push    r14
0x140003c96  push    r15
0x140003c98  sub     rsp, 60h
0x140003c9c  mov     r15, [rsp+78h+arg_20]
0x140003ca4  mov     r14, r9
0x140003ca7  mov     [r11+10h], rbp
0x140003cab  mov     rax, rdx
0x140003cae  mov     [r11+18h], rsi
0x140003cb2  mov     rbp, r8
0x140003cb5  xor     esi, esi
0x140003cb7  mov     byte ptr [r9], 0
0x140003cbb  test    byte ptr [rcx+30h], 20h
0x140003cbf  mov     [r11+20h], rdi
0x140003cc3  mov     rdi, rcx
0x140003cc6  jnz     loc_140003E02
0x140003ccc  lea     rdx, [r11+8]; ppwsz
0x140003cd0  mov     [r11+8], rsi
0x140003cd4  mov     rcx, rax; psz
0x140003cd7  call    cs:__imp_SHStrDupW
0x140003cdd  mov     ebx, eax
0x140003cdf  test    eax, eax
0x140003ce1  js      short loc_140003D21
0x140003ce3  mov     rcx, [rsp+78h+lpsz]; lpsz
0x140003ceb  call    cs:__imp_PathUnquoteSpacesW
0x140003cf1  mov     rcx, [rdi+18h]; hToken
0x140003cf5  call    cs:__imp_ImpersonateLoggedOnUser
0x140003cfb  test    eax, eax
0x140003cfd  jnz     loc_140003D93
0x140003d03  call    cs:__imp_GetLastError
0x140003d09  mov     ebx, eax
0x140003d0b  test    eax, eax
0x140003d0d  jg      loc_140003E1E
0x140003d13  mov     rcx, [rsp+78h+lpsz]; pv
0x140003d1b  call    cs:__imp_CoTaskMemFree
0x140003d21  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d28  lea     rax, WPP_GLOBAL_Control
0x140003d2f  mov     rdi, [rsp+78h+arg_18]
0x140003d37  mov     rsi, [rsp+78h+arg_10]
0x140003d3f  mov     rbp, [rsp+78h+arg_8]
0x140003d47  cmp     rcx, rax
0x140003d4a  jnz     short loc_140003D58
0x140003d4c  mov     eax, ebx
0x140003d4e  add     rsp, 60h
0x140003d52  pop     r15
0x140003d54  pop     r14
0x140003d56  pop     rbx
0x140003d57  retn
0x140003d58  test    byte ptr [rcx+1Ch], 2
0x140003d5c  jz      short loc_140003D4C
0x140003d5e  cmp     byte ptr [r14], 0
0x140003d62  lea     rdx, aFalse; "FALSE"
0x140003d69  mov     rcx, [rcx+10h]
0x140003d6d  lea     rax, aTrue; "TRUE"
0x140003d74  cmovz   rax, rdx
0x140003d78  mov     r9d, ebx
0x140003d7b  mov     [rsp+78h+var_50], rax
0x140003d80  mov     edx, 20h ; ' '
0x140003d85  mov     eax, [r15]
0x140003d88  mov     [rsp+78h+var_58], eax
0x140003d8c  call    WPP_SF_DdS
0x140003d91  jmp     short loc_140003D4C
0x140003d93  mov     r8d, [rdi+30h]
0x140003d97  test    r8b, 1
0x140003d9b  jnz     short loc_140003E10
0x140003d9d  mov     esi, 1000h
0x140003da2  mov     eax, [rdi+4]
0x140003da5  dec     eax
0x140003da7  cmp     eax, 1
0x140003daa  ja      short loc_140003E19
0x140003dac  mov     r9b, 1
0x140003daf  lea     rax, [r15+48h]
0x140003db3  and     r8b, 40h
0x140003db7  mov     [rsp+78h+var_28], rax
0x140003dbc  lea     rcx, [r15+40h]
0x140003dc0  mov     [rsp+78h+var_30], rcx
0x140003dc5  lea     rdx, [r15+10h]
0x140003dc9  mov     rcx, [rsp+78h+lpsz]
0x140003dd1  lea     r10, [r15+18h]
0x140003dd5  mov     [rsp+78h+var_38], rdx
0x140003dda  mov     rdx, rbp
0x140003ddd  mov     [rsp+78h+var_40], r10
0x140003de2  mov     [rsp+78h+var_48], r14
0x140003de7  mov     [rsp+78h+var_50], r15
0x140003dec  mov     [rsp+78h+var_58], esi
0x140003df0  call    ?CuiGetBinarySignature@@YAJPEBGPEAXEEW4SIGNATURE_INFO_FLAGS@@PEAW4_CONTEXT_SIGNATURE@@PEAEPEAPEAG5PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; CuiGetBinarySignature(ushort const *,void *,uchar,uchar,SIGNATURE_INFO_FLAGS,_CONTEXT_SIGNATURE *,uchar *,ushort * *,ushort * *,_CERT_CONTEXT const * *,void * *)
0x140003df5  mov     ebx, eax
0x140003df7  call    cs:__imp_RevertToSelf
0x140003dfd  jmp     loc_140003D13
0x140003e02  mov     dword ptr [r15], 1
0x140003e09  mov     ebx, esi
0x140003e0b  jmp     loc_140003D21
0x140003e10  bt      r8d, 0Ah
0x140003e15  jnb     short loc_140003DA2
0x140003e17  jmp     short loc_140003D9D
0x140003e19  xor     r9d, r9d
0x140003e1c  jmp     short loc_140003DAF
0x140003e1e  movzx   ebx, ax
0x140003e21  or      ebx, 80070000h
0x140003e27  jmp     loc_140003D13
```
