# DrQuerySpecialShare(ushort const *,ulong)

- ea: `0x14002c618`
- end: `0x14002c88d`
- name: `?DrQuerySpecialShare@@YAHPEBGK@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400254c0`

## callees

- `0x1400036c0`
- `0x140003b98`
- `0x14002c618`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c661`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c6ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c764`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c7b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c804`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c829`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c84e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c661`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c6ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c764`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c7b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c804`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c829`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c84e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002c737`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002c789`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002c7db`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002c737`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002c789`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002c7db`

## pseudocode

```c
__int64 __fastcall DrQuerySpecialShare(const unsigned __int16 *a1, int a2)
{
  wchar_t *v2; // r14
  const unsigned __int16 *v3; // rsi
  unsigned int v4; // ebx
  int v5; // edi
  int v6; // r15d
  int v7; // ebp
  HANDLE CurrentThreadId; // rax
  int v9; // eax
  HANDLE v10; // rax
  BOOLEAN v11; // al
  HANDLE v12; // rax
  __int64 v13; // rdx
  BOOLEAN v14; // al
  BOOLEAN v15; // al
  UNICODE_STRING String1; // [rsp+30h] [rbp-58h] BYREF

  v2 = 0;
  v3 = a1 + 1;
  v4 = 0;
  v5 = 0;
  String1 = 0;
  v6 = 1;
  v7 = a2 - 2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      89,
      WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
      CurrentThreadId,
      v7);
  }
  if ( v7 )
  {
    while ( 1 )
    {
      if ( *v3 == 92 )
      {
        if ( !v6 )
          break;
        v2 = (wchar_t *)v3;
        v6 = 0;
      }
      v9 = v5 + 2;
      if ( v6 )
        v9 = v5;
      v5 = v9;
      v7 -= 2;
      if ( !v7 )
        break;
      ++v3;
    }
    if ( v2 )
    {
      if ( v5 == 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v12 = PsGetCurrentThreadId();
          v13 = 91;
          goto LABEL_35;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v10 = PsGetCurrentThreadId();
          WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, v10, v5);
        }
        String1.Buffer = v2;
        String1.Length = v5;
        String1.MaximumLength = v5;
        v11 = RtlEqualUnicodeString(&String1, &s_PipeShareName, 1u);
        v4 = v11;
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v12 = PsGetCurrentThreadId();
            v13 = 93;
LABEL_35:
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, v13, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, v12);
          }
        }
        else
        {
          v14 = RtlEqualUnicodeString(&String1, &s_MailSlotShareName, 1u);
          v4 = v14;
          if ( v14 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v12 = PsGetCurrentThreadId();
              v13 = 94;
              goto LABEL_35;
            }
          }
          else
          {
            v15 = RtlEqualUnicodeString(&String1, &s_IpcShareName, 1u);
            v4 = v15;
            if ( v15
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v12 = PsGetCurrentThreadId();
              v13 = 95;
              goto LABEL_35;
            }
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v12 = PsGetCurrentThreadId();
      v13 = 90;
      goto LABEL_35;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14002c618  push    rbx
0x14002c61a  push    rbp
0x14002c61b  push    rsi
0x14002c61c  push    rdi
0x14002c61d  push    r12
0x14002c61f  push    r13
0x14002c621  push    r14
0x14002c623  push    r15
0x14002c625  sub     rsp, 48h
0x14002c629  xor     r14d, r14d
0x14002c62c  lea     rsi, [rcx+2]
0x14002c630  mov     ebp, edx
0x14002c632  xor     ebx, ebx
0x14002c634  xorps   xmm0, xmm0
0x14002c637  xor     edi, edi
0x14002c639  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x14002c63e  lea     r15d, [r14+1]
0x14002c642  add     ebp, 0FFFFFFFEh
0x14002c645  mov     rax, cs:WPP_GLOBAL_Control
0x14002c64c  lea     r13, WPP_GLOBAL_Control
0x14002c653  mov     r12b, 5
0x14002c656  cmp     rax, r13
0x14002c659  jz      short loc_14002C68E
0x14002c65b  cmp     [rax+29h], r12b
0x14002c65f  jb      short loc_14002C68E
0x14002c661  call    cs:__imp_PsGetCurrentThreadId
0x14002c668  nop     dword ptr [rax+rax+00h]
0x14002c66d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c674  lea     edx, [rbx+59h]
0x14002c677  mov     r9, rax
0x14002c67a  mov     [rsp+88h+var_68], ebp
0x14002c67e  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14002c685  mov     rcx, [rcx+18h]
0x14002c689  call    WPP_SF_qd
0x14002c68e  test    ebp, ebp
0x14002c690  jz      loc_14002C879
0x14002c696  mov     r12d, 5Ch ; '\'
0x14002c69c  cmp     [rsi], r12w
0x14002c6a0  jnz     short loc_14002C6AD
0x14002c6a2  test    r15d, r15d
0x14002c6a5  jz      short loc_14002C6C3
0x14002c6a7  mov     r14, rsi
0x14002c6aa  xor     r15d, r15d
0x14002c6ad  test    r15d, r15d
0x14002c6b0  lea     eax, [rdi+2]
0x14002c6b3  cmovnz  eax, edi
0x14002c6b6  mov     edi, eax
0x14002c6b8  add     ebp, 0FFFFFFFEh
0x14002c6bb  jz      short loc_14002C6C3
0x14002c6bd  add     rsi, 2
0x14002c6c1  jmp     short loc_14002C69C
0x14002c6c3  mov     r12b, 5
0x14002c6c6  test    r14, r14
0x14002c6c9  jz      loc_14002C83C
0x14002c6cf  cmp     edi, 2
0x14002c6d2  jz      loc_14002C817
0x14002c6d8  mov     rax, cs:WPP_GLOBAL_Control
0x14002c6df  cmp     rax, r13
0x14002c6e2  jz      short loc_14002C719
0x14002c6e4  cmp     [rax+29h], r12b
0x14002c6e8  jb      short loc_14002C719
0x14002c6ea  call    cs:__imp_PsGetCurrentThreadId
0x14002c6f1  nop     dword ptr [rax+rax+00h]
0x14002c6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c6fd  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14002c704  mov     edx, 5Ch ; '\'
0x14002c709  mov     [rsp+88h+var_68], edi
0x14002c70d  mov     r9, rax
0x14002c710  mov     rcx, [rcx+18h]
0x14002c714  call    WPP_SF_qd
0x14002c719  mov     r8b, 1; CaseInSensitive
0x14002c71c  mov     [rsp+88h+String1.Buffer], r14
0x14002c721  lea     rdx, ?s_PipeShareName@@3U_UNICODE_STRING@@A; String2
0x14002c728  mov     [rsp+88h+String1.Length], di
0x14002c72d  lea     rcx, [rsp+88h+String1]; String1
0x14002c732  mov     [rsp+88h+String1.MaximumLength], di
0x14002c737  call    cs:__imp_RtlEqualUnicodeString
0x14002c73e  nop     dword ptr [rax+rax+00h]
0x14002c743  movzx   ebx, al
0x14002c746  test    al, al
0x14002c748  jz      short loc_14002C77A
0x14002c74a  mov     rax, cs:WPP_GLOBAL_Control
0x14002c751  cmp     rax, r13
0x14002c754  jz      loc_14002C879
0x14002c75a  cmp     [rax+29h], r12b
0x14002c75e  jb      loc_14002C879
0x14002c764  call    cs:__imp_PsGetCurrentThreadId
0x14002c76b  nop     dword ptr [rax+rax+00h]
0x14002c770  mov     edx, 5Dh ; ']'
0x14002c775  jmp     loc_14002C85F
0x14002c77a  mov     r8b, 1; CaseInSensitive
0x14002c77d  lea     rdx, ?s_MailSlotShareName@@3U_UNICODE_STRING@@A; String2
0x14002c784  lea     rcx, [rsp+88h+String1]; String1
0x14002c789  call    cs:__imp_RtlEqualUnicodeString
0x14002c790  nop     dword ptr [rax+rax+00h]
0x14002c795  movzx   ebx, al
0x14002c798  test    al, al
0x14002c79a  jz      short loc_14002C7CC
0x14002c79c  mov     rax, cs:WPP_GLOBAL_Control
0x14002c7a3  cmp     rax, r13
0x14002c7a6  jz      loc_14002C879
0x14002c7ac  cmp     [rax+29h], r12b
0x14002c7b0  jb      loc_14002C879
0x14002c7b6  call    cs:__imp_PsGetCurrentThreadId
0x14002c7bd  nop     dword ptr [rax+rax+00h]
0x14002c7c2  mov     edx, 5Eh ; '^'
0x14002c7c7  jmp     loc_14002C85F
0x14002c7cc  mov     r8b, 1; CaseInSensitive
0x14002c7cf  lea     rdx, ?s_IpcShareName@@3U_UNICODE_STRING@@A; String2
0x14002c7d6  lea     rcx, [rsp+88h+String1]; String1
0x14002c7db  call    cs:__imp_RtlEqualUnicodeString
0x14002c7e2  nop     dword ptr [rax+rax+00h]
0x14002c7e7  movzx   ebx, al
0x14002c7ea  test    al, al
0x14002c7ec  jz      loc_14002C879
0x14002c7f2  mov     rax, cs:WPP_GLOBAL_Control
0x14002c7f9  cmp     rax, r13
0x14002c7fc  jz      short loc_14002C879
0x14002c7fe  cmp     [rax+29h], r12b
0x14002c802  jb      short loc_14002C879
0x14002c804  call    cs:__imp_PsGetCurrentThreadId
0x14002c80b  nop     dword ptr [rax+rax+00h]
0x14002c810  mov     edx, 5Fh ; '_'
0x14002c815  jmp     short loc_14002C85F
0x14002c817  mov     rax, cs:WPP_GLOBAL_Control
0x14002c81e  cmp     rax, r13
0x14002c821  jz      short loc_14002C879
0x14002c823  cmp     [rax+29h], r12b
0x14002c827  jb      short loc_14002C879
0x14002c829  call    cs:__imp_PsGetCurrentThreadId
0x14002c830  nop     dword ptr [rax+rax+00h]
0x14002c835  mov     edx, 5Bh ; '['
0x14002c83a  jmp     short loc_14002C85F
0x14002c83c  mov     rax, cs:WPP_GLOBAL_Control
0x14002c843  cmp     rax, r13
0x14002c846  jz      short loc_14002C879
0x14002c848  cmp     [rax+29h], r12b
0x14002c84c  jb      short loc_14002C879
0x14002c84e  call    cs:__imp_PsGetCurrentThreadId
0x14002c855  nop     dword ptr [rax+rax+00h]
0x14002c85a  mov     edx, 5Ah ; 'Z'
0x14002c85f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c866  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14002c86d  mov     r9, rax
0x14002c870  mov     rcx, [rcx+18h]
0x14002c874  call    WPP_SF_q
0x14002c879  mov     eax, ebx
0x14002c87b  add     rsp, 48h
0x14002c87f  pop     r15
0x14002c881  pop     r14
0x14002c883  pop     r13
0x14002c885  pop     r12
0x14002c887  pop     rdi
0x14002c888  pop     rsi
0x14002c889  pop     rbp
0x14002c88a  pop     rbx
0x14002c88b  retn
```
