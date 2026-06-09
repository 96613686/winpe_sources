# MRxDAVGetCompletePathName

- ea: `0x140002be4`
- end: `0x140002e9f`
- name: `MRxDAVGetCompletePathName`
- size: `699`
- prototype: `__int64 __fastcall(__int64, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400189a0`
- `0x14001ac20`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001838`
- `0x140002ac4`
- `0x140002be4`
- `0x140006900`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140002d57`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002dc6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002e1a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002e68`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002d57`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002dc6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002e1a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002e68`
- `ntoskrnl!ExAllocatePool2` at `0x140002d15`
- `ntoskrnl!ExAllocatePool2` at `0x140002d15`
- `ntoskrnl!_wcsnicmp` at `0x140002cd4`
- `ntoskrnl!_wcsnicmp` at `0x140002cd4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002c10`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002c10`

## pseudocode

```c
__int64 __fastcall MRxDAVGetCompletePathName(__int64 a1, unsigned int a2, struct _UNICODE_STRING *a3)
{
  __int16 *v3; // rdi
  unsigned int v6; // ebp
  unsigned __int16 v8; // bx
  __int64 v9; // rsi
  unsigned __int16 v10; // bx
  unsigned __int16 v11; // di
  _WORD *v12; // rsi
  size_t v13; // rbx
  WCHAR *Pool2; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdi
  HANDLE v20; // rax
  __int64 v21; // rbx
  HANDLE CurrentThreadId; // rax

  v3 = *(__int16 **)(a1 + 568);
  v6 = 0;
  RtlInitUnicodeString(a3, 0);
  if ( v3 && (v8 = *v3) != 0 )
  {
    v9 = *((_QWORD *)v3 + 1);
  }
  else
  {
    v8 = *(_WORD *)(a1 + 816);
    if ( v8 )
    {
      v9 = *(_QWORD *)(a1 + 824);
    }
    else
    {
      v8 = *(_WORD *)(a1 + 448);
      if ( !v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          CurrentThreadId = PsGetCurrentThreadId();
          WPP_SF_q(v21, 46, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, CurrentThreadId);
        }
        return v6;
      }
      v9 = *(_QWORD *)(a1 + 456);
    }
  }
  v10 = v8 >> 1;
  if ( v9 && v10 <= 0x104u )
  {
    v11 = 0;
    if ( v10 )
    {
      while ( *(_WORD *)(v9 + 2LL * v11) == 92 )
      {
        if ( ++v11 >= v10 )
          return v6;
      }
      while ( *(_WORD *)(v9 + 2LL * v11) != 92 )
      {
        if ( ++v11 >= v10 )
          return v6;
      }
      if ( (unsigned int)v11 + 11 > v10
        || _wcsnicmp((const wchar_t *)(v9 + 2LL * v11), L"\\DavWWWRoot", 0xBu)
        || (v11 += 11, v11 < v10) )
      {
        v12 = (_WORD *)(v9 + 2LL * v11);
        if ( *v12 == 92 )
        {
          v13 = (unsigned __int16)(2 * (v10 - v11));
          Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned int)v13, a2);
          a3->Buffer = Pool2;
          if ( Pool2 )
          {
            memmove(Pool2, v12, v13);
            a3->Length = v13;
            a3->MaximumLength = v13;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v18 = (unsigned int)PsGetCurrentThreadId();
              WPP_SF_qZ(v17, 49, (unsigned int)WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v18, (__int64)a3);
            }
          }
          else
          {
            v6 = -1073741670;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v16 = PsGetCurrentThreadId();
              WPP_SF_qD(v15, 48, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v16, -1073741670);
            }
          }
        }
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v20 = PsGetCurrentThreadId();
    WPP_SF_qqD(v19, 47, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v20, v9, v10);
  }
  return v6;
}

```

## disassembly

```asm
0x140002be4  push    rbx
0x140002be6  push    rbp
0x140002be7  push    rsi
0x140002be8  push    rdi
0x140002be9  push    r12
0x140002beb  push    r13
0x140002bed  push    r14
0x140002bef  push    r15
0x140002bf1  sub     rsp, 38h
0x140002bf5  mov     rdi, [rcx+238h]
0x140002bfc  mov     r15d, edx
0x140002bff  mov     rsi, rcx
0x140002c02  xor     r12d, r12d
0x140002c05  xor     edx, edx; SourceString
0x140002c07  mov     rcx, r8; DestinationString
0x140002c0a  mov     ebp, r12d
0x140002c0d  mov     r14, r8
0x140002c10  call    cs:__imp_RtlInitUnicodeString
0x140002c17  nop     dword ptr [rax+rax+00h]
0x140002c1c  test    rdi, rdi
0x140002c1f  jz      short loc_140002C2F
0x140002c21  movzx   ebx, word ptr [rdi]
0x140002c24  test    bx, bx
0x140002c27  jz      short loc_140002C2F
0x140002c29  mov     rsi, [rdi+8]
0x140002c2d  jmp     short loc_140002C5B
0x140002c2f  movzx   ebx, word ptr [rsi+330h]
0x140002c36  test    bx, bx
0x140002c39  jz      short loc_140002C44
0x140002c3b  mov     rsi, [rsi+338h]
0x140002c42  jmp     short loc_140002C5B
0x140002c44  movzx   ebx, word ptr [rsi+1C0h]
0x140002c4b  test    bx, bx
0x140002c4e  jz      loc_140002E48
0x140002c54  mov     rsi, [rsi+1C8h]
0x140002c5b  shr     bx, 1
0x140002c5e  test    rsi, rsi
0x140002c61  jz      loc_140002DF3
0x140002c67  mov     eax, 104h
0x140002c6c  cmp     bx, ax
0x140002c6f  ja      loc_140002DF3
0x140002c75  mov     edi, r12d
0x140002c78  cmp     r12w, bx
0x140002c7c  jnb     loc_140002E8B
0x140002c82  movzx   eax, di
0x140002c85  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x140002c8a  jnz     short loc_140002C99
0x140002c8c  inc     di
0x140002c8f  cmp     di, bx
0x140002c92  jb      short loc_140002C82
0x140002c94  jmp     loc_140002E8B
0x140002c99  movzx   eax, di
0x140002c9c  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x140002ca1  jz      short loc_140002CB0
0x140002ca3  inc     di
0x140002ca6  cmp     di, bx
0x140002ca9  jb      short loc_140002C99
0x140002cab  jmp     loc_140002E8B
0x140002cb0  movzx   ecx, di
0x140002cb3  mov     r13d, 0Bh
0x140002cb9  add     ecx, r13d
0x140002cbc  movzx   eax, bx
0x140002cbf  cmp     ecx, eax
0x140002cc1  ja      short loc_140002CF1
0x140002cc3  movzx   eax, di
0x140002cc6  lea     rdx, aDavwwwroot; "\\DavWWWRoot"
0x140002ccd  mov     r8d, r13d; MaxCount
0x140002cd0  lea     rcx, [rsi+rax*2]; Str1
0x140002cd4  call    cs:__imp__wcsnicmp
0x140002cdb  nop     dword ptr [rax+rax+00h]
0x140002ce0  test    eax, eax
0x140002ce2  jnz     short loc_140002CF1
0x140002ce4  add     di, r13w
0x140002ce8  cmp     di, bx
0x140002ceb  jnb     loc_140002E8B
0x140002cf1  movzx   eax, di
0x140002cf4  lea     rsi, [rsi+rax*2]
0x140002cf8  cmp     word ptr [rsi], 5Ch ; '\'
0x140002cfc  jnz     loc_140002E8B
0x140002d02  sub     bx, di
0x140002d05  mov     r8d, r15d
0x140002d08  add     bx, bx
0x140002d0b  mov     ecx, 102h
0x140002d10  movzx   ebx, bx
0x140002d13  mov     edx, ebx
0x140002d15  call    cs:__imp_ExAllocatePool2
0x140002d1c  nop     dword ptr [rax+rax+00h]
0x140002d21  mov     [r14+8], rax
0x140002d25  test    rax, rax
0x140002d28  jnz     short loc_140002D87
0x140002d2a  mov     ebp, 0C000009Ah
0x140002d2f  mov     rbx, cs:WPP_GLOBAL_Control
0x140002d36  lea     rax, WPP_GLOBAL_Control
0x140002d3d  cmp     rbx, rax
0x140002d40  jz      loc_140002E8B
0x140002d46  test    dword ptr [rbx+2Ch], 2000h
0x140002d4d  jz      loc_140002E8B
0x140002d53  mov     rbx, [rbx+18h]
0x140002d57  call    cs:__imp_PsGetCurrentThreadId
0x140002d5e  nop     dword ptr [rax+rax+00h]
0x140002d63  mov     edx, 30h ; '0'
0x140002d68  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140002d70  mov     r9, rax
0x140002d73  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140002d7a  mov     rcx, rbx
0x140002d7d  call    WPP_SF_qD
0x140002d82  jmp     loc_140002E8B
0x140002d87  mov     r8, rbx; Size
0x140002d8a  mov     rdx, rsi; Src
0x140002d8d  mov     rcx, rax; void *
0x140002d90  call    memmove
0x140002d95  mov     [r14], bx
0x140002d99  mov     [r14+2], bx
0x140002d9e  mov     rbx, cs:WPP_GLOBAL_Control
0x140002da5  lea     rax, WPP_GLOBAL_Control
0x140002dac  cmp     rbx, rax
0x140002daf  jz      loc_140002E8B
0x140002db5  test    dword ptr [rbx+2Ch], 2000h
0x140002dbc  jz      loc_140002E8B
0x140002dc2  mov     rbx, [rbx+18h]
0x140002dc6  call    cs:__imp_PsGetCurrentThreadId
0x140002dcd  nop     dword ptr [rax+rax+00h]
0x140002dd2  mov     edx, 31h ; '1'
0x140002dd7  mov     [rsp+78h+var_58], r14
0x140002ddc  mov     r9, rax
0x140002ddf  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140002de6  mov     rcx, rbx
0x140002de9  call    WPP_SF_qZ
0x140002dee  jmp     loc_140002E8B
0x140002df3  mov     rdi, cs:WPP_GLOBAL_Control
0x140002dfa  lea     rax, WPP_GLOBAL_Control
0x140002e01  cmp     rdi, rax
0x140002e04  jz      loc_140002E8B
0x140002e0a  test    dword ptr [rdi+2Ch], 2000h
0x140002e11  jz      short loc_140002E8B
0x140002e13  mov     rdi, [rdi+18h]
0x140002e17  movzx   ebx, bx
0x140002e1a  call    cs:__imp_PsGetCurrentThreadId
0x140002e21  nop     dword ptr [rax+rax+00h]
0x140002e26  mov     edx, 2Fh ; '/'
0x140002e2b  mov     [rsp+78h+var_50], ebx
0x140002e2f  mov     r9, rax
0x140002e32  mov     [rsp+78h+var_58], rsi
0x140002e37  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140002e3e  mov     rcx, rdi
0x140002e41  call    WPP_SF_qqD
0x140002e46  jmp     short loc_140002E8B
0x140002e48  mov     rbx, cs:WPP_GLOBAL_Control
0x140002e4f  lea     rax, WPP_GLOBAL_Control
0x140002e56  cmp     rbx, rax
0x140002e59  jz      short loc_140002E8B
0x140002e5b  test    dword ptr [rbx+2Ch], 2000h
0x140002e62  jz      short loc_140002E8B
0x140002e64  mov     rbx, [rbx+18h]
0x140002e68  call    cs:__imp_PsGetCurrentThreadId
0x140002e6f  nop     dword ptr [rax+rax+00h]
0x140002e74  mov     edx, 2Eh ; '.'
0x140002e79  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140002e80  mov     r9, rax
0x140002e83  mov     rcx, rbx
0x140002e86  call    WPP_SF_q
0x140002e8b  mov     eax, ebp
0x140002e8d  add     rsp, 38h
0x140002e91  pop     r15
0x140002e93  pop     r14
0x140002e95  pop     r13
0x140002e97  pop     r12
0x140002e99  pop     rdi
0x140002e9a  pop     rsi
0x140002e9b  pop     rbp
0x140002e9c  pop     rbx
0x140002e9d  retn
```
