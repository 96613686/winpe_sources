# DrSavePhoneNumber

- ea: `0x18000cfb0`
- end: `0x18000d1a5`
- name: `DrSavePhoneNumber`
- size: `501`
- prototype: `wchar_t *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cbb0`

## callees

- `0x18000cfb0`
- `0x18002a81c`
- `0x18003b540`
- `0x18003bea0`
- `0x18003c860`
- `0x18003ce6c`
- `0x180048048`
- `0x180048364`
- `0x180048f0c`
- `0x18004d0d2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000d16d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000d18d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000d16d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000d18d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d00d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d00d`
- `RASAPI32!CreatePhoneNode` at `0x18000d12f`
- `RASAPI32!CreatePhoneNode` at `0x18000d12f`

## pseudocode

```c
wchar_t *__fastcall DrSavePhoneNumber(__int64 a1, __int64 a2)
{
  wchar_t *result; // rax
  wchar_t *v5; // rdi
  const WCHAR **ItemDataPtr; // rax
  const WCHAR **v7; // r14
  const WCHAR *v8; // rdx
  __int64 v9; // rcx
  int v10; // edx
  __int64 v11; // rcx
  int v12; // r15d
  const WCHAR *v13; // rbx
  __int64 i; // rbx
  __int64 PhoneNode; // rax
  __int64 v16; // rbx
  va_list Arguments[9]; // [rsp+30h] [rbp-A8h] BYREF
  int v18; // [rsp+78h] [rbp-60h]

  result = (wchar_t *)GetText(*(HWND *)(a1 + 64));
  v5 = result;
  if ( result )
  {
    ItemDataPtr = (const WCHAR **)ComboBox_GetItemDataPtr(
                                    *(HWND *)(a1 + 64),
                                    *(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL));
    v7 = ItemDataPtr;
    if ( ItemDataPtr )
      v8 = *ItemDataPtr;
    else
      v8 = &WideCharStr;
    if ( lstrcmpW(v5, v8) || (v9 = *(_QWORD *)(a1 + 168), *(_DWORD *)(v9 + 176) != *(_DWORD *)(a1 + 176)) )
    {
      memset_0(Arguments, 0, 0x68u);
      v10 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 168) + 168LL) + 16LL);
      v11 = *(_QWORD *)(a2 + 440);
      v12 = *(_DWORD *)(*(_QWORD *)(v11 + 32) + 16LL);
      v18 = 292;
      if ( v10 == 1
        && (v12 <= 1 || *(_DWORD *)(v11 + 40))
        && (unsigned int)MsgDlgUtil(*(HWND *)(a1 + 8), 0x1C7u, Arguments, g_hinstDll, 0x169u) == 6 )
      {
        *(_DWORD *)(*(_QWORD *)(a2 + 440) + 532LL) = 1;
        if ( v7 )
        {
          v13 = v7[1];
          Free0(*v7);
          *v7 = (const WCHAR *)StrDup(v5);
          Free0(*((_QWORD *)v13 + 2));
          *((_QWORD *)v13 + 2) = StrDup(v5);
          *((_DWORD *)v13 + 6) = 0;
          if ( v12 > 1 )
          {
            for ( i = **(_QWORD **)(*(_QWORD *)(a2 + 440) + 32LL); i; i = *(_QWORD *)(i + 8) )
              CopyLinkPhoneNumberInfo(i, *(_QWORD *)(a1 + 160));
          }
        }
        else
        {
          PhoneNode = CreatePhoneNode();
          if ( PhoneNode )
            DtlAddNodeFirst(*(_QWORD *)(*(_QWORD *)(a1 + 168) + 168LL), PhoneNode);
        }
      }
    }
    else if ( *(_DWORD *)(v9 + 184) )
    {
      return (wchar_t *)GlobalFree(v5);
    }
    if ( !*v5 )
    {
      v16 = StrDup(L" ");
      if ( v16 )
      {
        GlobalFree(v5);
        v5 = (wchar_t *)v16;
      }
    }
    StringCchCopyWrapW((wchar_t *)(a2 + 1006), 0x81u, v5);
    return (wchar_t *)GlobalFree(v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000cfb0  push    rbx
0x18000cfb2  push    rbp
0x18000cfb3  push    rsi
0x18000cfb4  push    rdi
0x18000cfb5  push    r12
0x18000cfb7  push    r14
0x18000cfb9  push    r15
0x18000cfbb  sub     rsp, 0A0h
0x18000cfc2  mov     rsi, rcx
0x18000cfc5  mov     rbp, rdx
0x18000cfc8  mov     rcx, [rcx+40h]; hWnd
0x18000cfcc  call    GetText
0x18000cfd1  xor     r12d, r12d
0x18000cfd4  mov     rdi, rax
0x18000cfd7  test    rax, rax
0x18000cfda  jz      loc_18000D193
0x18000cfe0  mov     rdx, [rsi+0A8h]
0x18000cfe7  mov     rcx, [rsi+40h]
0x18000cfeb  mov     edx, [rdx+0B0h]
0x18000cff1  call    ComboBox_GetItemDataPtr
0x18000cff6  mov     r14, rax
0x18000cff9  test    rax, rax
0x18000cffc  jz      short loc_18000D003
0x18000cffe  mov     rdx, [rax]
0x18000d001  jmp     short loc_18000D00A
0x18000d003  lea     rdx, WideCharStr; lpString2
0x18000d00a  mov     rcx, rdi; lpString1
0x18000d00d  call    cs:__imp_lstrcmpW
0x18000d013  test    eax, eax
0x18000d015  jnz     short loc_18000D03E
0x18000d017  mov     rcx, [rsi+0A8h]
0x18000d01e  mov     eax, [rsi+0B0h]
0x18000d024  cmp     [rcx+0B0h], eax
0x18000d02a  jnz     short loc_18000D03E
0x18000d02c  cmp     [rcx+0B8h], r12d
0x18000d033  jnz     loc_18000D18A
0x18000d039  jmp     loc_18000D150
0x18000d03e  xor     edx, edx; Val
0x18000d040  lea     rcx, [rsp+0D8h+Arguments]; void *
0x18000d045  lea     r8d, [rdx+68h]; Size
0x18000d049  call    memset_0
0x18000d04e  mov     rax, [rsi+0A8h]
0x18000d055  mov     rcx, [rax+0A8h]
0x18000d05c  mov     edx, [rcx+10h]
0x18000d05f  mov     rcx, [rbp+1B8h]
0x18000d066  mov     rax, [rcx+20h]
0x18000d06a  mov     r15d, [rax+10h]
0x18000d06e  mov     [rsp+0D8h+var_60], 124h
0x18000d076  cmp     edx, 1
0x18000d079  jnz     loc_18000D150
0x18000d07f  cmp     r15d, edx
0x18000d082  jle     short loc_18000D08E
0x18000d084  cmp     [rcx+28h], r12d
0x18000d088  jz      loc_18000D150
0x18000d08e  mov     r9, cs:g_hinstDll; hInstance
0x18000d095  lea     r8, [rsp+0D8h+Arguments]; Arguments
0x18000d09a  mov     rcx, [rsi+8]; hWnd
0x18000d09e  mov     edx, 1C7h; uID
0x18000d0a3  mov     [rsp+0D8h+var_B8], 169h; UINT
0x18000d0ab  call    MsgDlgUtil
0x18000d0b0  cmp     eax, 6
0x18000d0b3  jnz     loc_18000D150
0x18000d0b9  mov     rax, [rbp+1B8h]
0x18000d0c0  mov     dword ptr [rax+214h], 1
0x18000d0ca  test    r14, r14
0x18000d0cd  jz      short loc_18000D12F
0x18000d0cf  mov     rcx, [r14]
0x18000d0d2  mov     rbx, [r14+8]
0x18000d0d6  call    Free0
0x18000d0db  mov     rcx, rdi; pszSrc
0x18000d0de  call    StrDup
0x18000d0e3  mov     [r14], rax
0x18000d0e6  mov     rcx, [rbx+10h]
0x18000d0ea  call    Free0
0x18000d0ef  mov     rcx, rdi; pszSrc
0x18000d0f2  call    StrDup
0x18000d0f7  mov     [rbx+10h], rax
0x18000d0fb  mov     [rbx+18h], r12d
0x18000d0ff  cmp     r15d, 1
0x18000d103  jle     short loc_18000D150
0x18000d105  mov     rax, [rbp+1B8h]
0x18000d10c  mov     rcx, [rax+20h]
0x18000d110  mov     rbx, [rcx]
0x18000d113  jmp     short loc_18000D128
0x18000d115  mov     rdx, [rsi+0A0h]
0x18000d11c  mov     rcx, rbx
0x18000d11f  call    CopyLinkPhoneNumberInfo
0x18000d124  mov     rbx, [rbx+8]
0x18000d128  test    rbx, rbx
0x18000d12b  jnz     short loc_18000D115
0x18000d12d  jmp     short loc_18000D150
0x18000d12f  call    cs:__imp_CreatePhoneNode
0x18000d135  test    rax, rax
0x18000d138  jz      short loc_18000D150
0x18000d13a  mov     rcx, [rsi+0A8h]
0x18000d141  mov     rdx, rax
0x18000d144  mov     rcx, [rcx+0A8h]
0x18000d14b  call    DtlAddNodeFirst
0x18000d150  cmp     [rdi], r12w
0x18000d154  jnz     short loc_18000D176
0x18000d156  lea     rcx, asc_180053C48; " "
0x18000d15d  call    StrDup
0x18000d162  mov     rbx, rax
0x18000d165  test    rax, rax
0x18000d168  jz      short loc_18000D176
0x18000d16a  mov     rcx, rdi; hMem
0x18000d16d  call    cs:__imp_GlobalFree
0x18000d173  mov     rdi, rbx
0x18000d176  lea     rcx, [rbp+3EEh]
0x18000d17d  mov     r8, rdi
0x18000d180  mov     edx, 81h
0x18000d185  call    StringCchCopyWrapW
0x18000d18a  mov     rcx, rdi; hMem
0x18000d18d  call    cs:__imp_GlobalFree
0x18000d193  add     rsp, 0A0h
0x18000d19a  pop     r15
0x18000d19c  pop     r14
0x18000d19e  pop     r12
0x18000d1a0  pop     rdi
0x18000d1a1  pop     rsi
0x18000d1a2  pop     rbp
0x18000d1a3  pop     rbx
0x18000d1a4  retn
```
