# KerbInteractiveUnlockLogonPack(_KERB_INTERACTIVE_UNLOCK_LOGON const &,uchar * *,ulong *)

- ea: `0x18002db94`
- end: `0x18002dc91`
- name: `?KerbInteractiveUnlockLogonPack@@YAJAEBU_KERB_INTERACTIVE_UNLOCK_LOGON@@PEAPEAEPEAK@Z`
- size: `253`
- prototype: `__int64 __fastcall(const struct _KERB_INTERACTIVE_UNLOCK_LOGON *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020040`

## callees

- `0x18002db94`
- `0x18002dffc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dbc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dbc2`

## pseudocode

```c
__int64 __fastcall KerbInteractiveUnlockLogonPack(
        const struct _KERB_INTERACTIVE_UNLOCK_LOGON *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned int v6; // ebp
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  char *v9; // rbx
  unsigned int Length; // ecx
  __int64 v11; // rax
  char *v12; // rbx
  unsigned int v13; // ecx
  size_t v14; // r8
  char *v15; // rbx
  __int64 result; // rax

  v6 = a1->Logon.Password.Length + a1->Logon.LogonDomainName.Length + a1->Logon.UserName.Length + 64;
  v7 = CoTaskMemAlloc(v6);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v9 = (char *)(v7 + 8);
  v7[7] = 0;
  *(_DWORD *)v7 = a1->Logon.MessageType;
  *((_WORD *)v7 + 32) = 0;
  Length = a1->Logon.LogonDomainName.Length;
  *((_WORD *)v7 + 4) = Length;
  *((_WORD *)v7 + 5) = a1->Logon.LogonDomainName.Length;
  v7[2] = v7 + 8;
  memcpy_0(v7 + 8, a1->Logon.LogonDomainName.Buffer, Length);
  v11 = *((unsigned __int16 *)v8 + 4);
  v8[2] = 64;
  v12 = &v9[v11];
  v13 = a1->Logon.UserName.Length;
  *((_WORD *)v8 + 12) = v13;
  *((_WORD *)v8 + 13) = a1->Logon.UserName.Length;
  v8[4] = v12;
  memcpy_0(v12, a1->Logon.UserName.Buffer, v13);
  v8[4] = v12 - (char *)v8;
  v14 = a1->Logon.Password.Length;
  v15 = &v12[*((unsigned __int16 *)v8 + 12)];
  *((_WORD *)v8 + 20) = v14;
  *((_WORD *)v8 + 21) = a1->Logon.Password.Length;
  v8[6] = v15;
  memcpy_0(v15, a1->Logon.Password.Buffer, v14);
  v8[6] = v15 - (char *)v8;
  result = 0;
  *a2 = (unsigned __int8 *)v8;
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x18002db94  push    rbx
0x18002db96  push    rbp
0x18002db97  push    rsi
0x18002db98  push    rdi
0x18002db99  push    r14
0x18002db9b  push    r15
0x18002db9d  sub     rsp, 28h
0x18002dba1  movzx   r9d, word ptr [rcx+8]
0x18002dba6  mov     rdi, rcx
0x18002dba9  movzx   eax, word ptr [rcx+28h]
0x18002dbad  mov     r14, r8
0x18002dbb0  movzx   ebp, word ptr [rcx+18h]
0x18002dbb4  add     r9d, eax
0x18002dbb7  add     ebp, 40h ; '@'
0x18002dbba  mov     r15, rdx
0x18002dbbd  add     ebp, r9d
0x18002dbc0  mov     ecx, ebp; cb
0x18002dbc2  call    cs:__imp_CoTaskMemAlloc
0x18002dbc8  mov     rsi, rax
0x18002dbcb  test    rax, rax
0x18002dbce  jz      loc_18002DC7F
0x18002dbd4  xor     eax, eax
0x18002dbd6  lea     rbx, [rsi+40h]
0x18002dbda  mov     [rsi+38h], rax
0x18002dbde  mov     ecx, [rdi]
0x18002dbe0  mov     [rsi], ecx
0x18002dbe2  mov     [rbx], ax
0x18002dbe5  movzx   ecx, word ptr [rdi+8]
0x18002dbe9  mov     [rsi+8], cx
0x18002dbed  mov     r8d, ecx; Size
0x18002dbf0  movzx   eax, word ptr [rdi+8]
0x18002dbf4  mov     rcx, rbx; void *
0x18002dbf7  mov     [rsi+0Ah], ax
0x18002dbfb  mov     [rsi+10h], rbx
0x18002dbff  mov     rdx, [rdi+10h]; Src
0x18002dc03  call    memcpy_0
0x18002dc08  movzx   eax, word ptr [rsi+8]
0x18002dc0c  mov     qword ptr [rsi+10h], 40h ; '@'
0x18002dc14  add     rbx, rax
0x18002dc17  movzx   ecx, word ptr [rdi+18h]
0x18002dc1b  mov     [rsi+18h], cx
0x18002dc1f  mov     r8d, ecx; Size
0x18002dc22  movzx   eax, word ptr [rdi+18h]
0x18002dc26  mov     rcx, rbx; void *
0x18002dc29  mov     [rsi+1Ah], ax
0x18002dc2d  mov     [rsi+20h], rbx
0x18002dc31  mov     rdx, [rdi+20h]; Src
0x18002dc35  call    memcpy_0
0x18002dc3a  mov     rax, rbx
0x18002dc3d  sub     rax, rsi
0x18002dc40  mov     [rsi+20h], rax
0x18002dc44  movzx   ecx, word ptr [rdi+28h]
0x18002dc48  movzx   eax, word ptr [rsi+18h]
0x18002dc4c  mov     r8d, ecx; Size
0x18002dc4f  add     rbx, rax
0x18002dc52  mov     [rsi+28h], cx
0x18002dc56  movzx   eax, word ptr [rdi+28h]
0x18002dc5a  mov     rcx, rbx; void *
0x18002dc5d  mov     [rsi+2Ah], ax
0x18002dc61  mov     [rsi+30h], rbx
0x18002dc65  mov     rdx, [rdi+30h]; Src
0x18002dc69  call    memcpy_0
0x18002dc6e  sub     rbx, rsi
0x18002dc71  mov     [rsi+30h], rbx
0x18002dc75  xor     eax, eax
0x18002dc77  mov     [r15], rsi
0x18002dc7a  mov     [r14], ebp
0x18002dc7d  jmp     short loc_18002DC84
0x18002dc7f  mov     eax, 8007000Eh
0x18002dc84  add     rsp, 28h
0x18002dc88  pop     r15
0x18002dc8a  pop     r14
0x18002dc8c  pop     rdi
0x18002dc8d  pop     rsi
0x18002dc8e  pop     rbp
0x18002dc8f  pop     rbx
0x18002dc90  retn
```
