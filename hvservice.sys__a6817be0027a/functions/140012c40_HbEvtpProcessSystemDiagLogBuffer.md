# HbEvtpProcessSystemDiagLogBuffer

- ea: `0x140012c40`
- end: `0x140012e95`
- name: `HbEvtpProcessSystemDiagLogBuffer`
- size: `597`
- prototype: `char __fastcall(__int64, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013ef0`

## callees

- `0x140002ae0`
- `0x140002c00`
- `0x140012c40`
- `0x140012e9c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140012e5f`
- `ntoskrnl!EtwWriteTransfer` at `0x140012e5f`

## pseudocode

```c
char __fastcall HbEvtpProcessSystemDiagLogBuffer(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 v3; // rdi
  int v6; // r15d
  unsigned int v7; // ecx
  unsigned int v8; // ebp
  unsigned __int16 *v9; // rdx
  __int64 v10; // rbx
  int v11; // ecx
  bool v12; // cf
  unsigned __int64 v13; // rax
  signed __int32 v15[8]; // [rsp+0h] [rbp-C8h] BYREF
  unsigned int v16; // [rsp+30h] [rbp-98h]
  __int64 v17; // [rsp+38h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-78h] BYREF
  void *v20; // [rsp+60h] [rbp-68h]
  int v21; // [rsp+68h] [rbp-60h]
  int v22; // [rsp+6Ch] [rbp-5Ch]
  const char *v23; // [rsp+70h] [rbp-58h]
  __int64 v24; // [rsp+78h] [rbp-50h]
  __int64 *v25; // [rsp+80h] [rbp-48h]
  __int64 v26; // [rsp+88h] [rbp-40h]

  v3 = *a2;
  v6 = *(_DWORD *)(*a2 + 44);
  if ( *(_QWORD *)(*a2 + 16) == qword_140009480 )
  {
    v7 = dword_140009488;
    v8 = *(_DWORD *)(*a2 + 48) + 72;
    if ( v8 > dword_140009488 )
    {
      while ( (unsigned __int64)v7 + 16 <= *(unsigned int *)(a1 + 4) )
      {
        v9 = (unsigned __int16 *)(v3 + v7);
        if ( !v9[3] )
          break;
        v10 = v9[2];
        if ( (unsigned int)v10 < 0x10
          || v10 + (unsigned __int64)(unsigned int)dword_140009488 > *(unsigned int *)(a1 + 4) )
        {
          break;
        }
        memmove(P, v9, v9[2]);
        _InterlockedOr(v15, 0);
        if ( *(_QWORD *)(v3 + 16) != qword_140009480 )
          goto LABEL_15;
        HbEvtpProcessSystemDiagLogEntry();
        v11 = dword_140009488;
        ++*a3;
        v7 = ((v10 + 7) & 0xFFFFFFF8) + v11;
        v12 = *a3 < 0x1F4u;
        dword_140009488 = v7;
        if ( !v12 )
          return 1;
        if ( v8 <= v7 )
          goto LABEL_10;
      }
      return 0;
    }
LABEL_10:
    if ( v6 != 3 )
      return 0;
    if ( v7 < v8 )
      return 0;
    v13 = *(_QWORD *)(*(_QWORD *)(112LL * *(unsigned int *)(v3 + 56) + *(_QWORD *)(a1 + 32)) + 16LL);
    if ( v13 <= qword_140009480 )
      return 0;
    dword_14000948C = *(_DWORD *)(v3 + 56);
    qword_140009480 = v13;
    dword_140009488 = 72;
  }
  else
  {
LABEL_15:
    dword_14000948C = -1;
    if ( (unsigned int)dword_140009050 > 5 )
    {
      v24 = 16;
      EventDescriptor.Keyword = 0;
      v23 = "Buffer overflow";
      v17 = qword_140009480;
      v26 = 8;
      v25 = &v17;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_140009058;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_140009058;
      v20 = &unk_140007448;
      UserData.Reserved = 2;
      v21 = 50;
      v22 = 1;
      v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140012c40  mov     [rsp+arg_0], rbx
0x140012c45  push    rbp
0x140012c46  push    rsi
0x140012c47  push    rdi
0x140012c48  push    r14
0x140012c4a  push    r15
0x140012c4c  sub     rsp, 0A0h
0x140012c53  mov     rax, cs:__security_cookie
0x140012c5a  xor     rax, rsp
0x140012c5d  mov     [rsp+0C8h+var_38], rax
0x140012c65  mov     rdi, [rdx]
0x140012c68  mov     r14, r8
0x140012c6b  mov     rsi, rcx
0x140012c6e  mov     r15d, [rdi+2Ch]
0x140012c72  mov     ebp, [rdi+30h]
0x140012c75  mov     rax, [rdi+10h]
0x140012c79  cmp     rax, cs:qword_140009480
0x140012c80  jnz     loc_140012D7F
0x140012c86  mov     ecx, cs:dword_140009488
0x140012c8c  add     ebp, 48h ; 'H'
0x140012c8f  cmp     ebp, ecx
0x140012c91  jbe     loc_140012D36
0x140012c97  nop     word ptr [rax+rax+00000000h]
0x140012ca0  mov     eax, [rsi+4]
0x140012ca3  mov     edx, ecx
0x140012ca5  lea     rcx, [rdx+10h]
0x140012ca9  cmp     rcx, rax
0x140012cac  ja      loc_140012D78
0x140012cb2  add     rdx, rdi; Src
0x140012cb5  movzx   eax, word ptr [rdx+6]
0x140012cb9  test    ax, ax
0x140012cbc  jz      loc_140012D78
0x140012cc2  movzx   ebx, word ptr [rdx+4]
0x140012cc6  cmp     ebx, 10h
0x140012cc9  jb      loc_140012D78
0x140012ccf  mov     ecx, cs:dword_140009488
0x140012cd5  mov     r8d, ebx; Size
0x140012cd8  mov     eax, [rsi+4]
0x140012cdb  add     rcx, rbx
0x140012cde  cmp     rcx, rax
0x140012ce1  ja      loc_140012D78
0x140012ce7  mov     rcx, cs:P; void *
0x140012cee  call    memmove
0x140012cf3  lock or [rsp+0C8h+var_C8], 0
0x140012cf8  mov     rax, [rdi+10h]
0x140012cfc  cmp     rax, cs:qword_140009480
0x140012d03  jnz     short loc_140012D7F
0x140012d05  call    HbEvtpProcessSystemDiagLogEntry
0x140012d0a  mov     ecx, cs:dword_140009488
0x140012d10  lea     eax, [rbx+7]
0x140012d13  inc     qword ptr [r14]
0x140012d16  and     eax, 0FFFFFFF8h
0x140012d19  add     ecx, eax
0x140012d1b  cmp     qword ptr [r14], 1F4h
0x140012d22  mov     cs:dword_140009488, ecx
0x140012d28  jnb     loc_140012E6B
0x140012d2e  cmp     ebp, ecx
0x140012d30  ja      loc_140012CA0
0x140012d36  cmp     r15d, 3
0x140012d3a  jnz     short loc_140012D78
0x140012d3c  cmp     ecx, ebp
0x140012d3e  jb      short loc_140012D78
0x140012d40  mov     rax, [rsi+20h]
0x140012d44  mov     edx, [rdi+38h]
0x140012d47  imul    rcx, rdx, 70h ; 'p'
0x140012d4b  mov     rcx, [rcx+rax]
0x140012d4f  mov     rax, [rcx+10h]
0x140012d53  cmp     rax, cs:qword_140009480
0x140012d5a  jbe     short loc_140012D78
0x140012d5c  mov     cs:dword_14000948C, edx
0x140012d62  mov     cs:qword_140009480, rax
0x140012d69  mov     cs:dword_140009488, 48h ; 'H'
0x140012d73  jmp     loc_140012E6B
0x140012d78  xor     al, al
0x140012d7a  jmp     loc_140012E6D
0x140012d7f  mov     eax, cs:dword_140009050
0x140012d85  mov     cs:dword_14000948C, 0FFFFFFFFh
0x140012d8f  cmp     eax, 5
0x140012d92  jbe     loc_140012E6B
0x140012d98  xor     ecx, ecx
0x140012d9a  mov     [rsp+0C8h+var_50], 10h
0x140012da3  mov     [rsp+0C8h+EventDescriptor.Keyword], rcx
0x140012da8  lea     rax, aBufferOverflow; "Buffer overflow"
0x140012daf  mov     [rsp+0C8h+var_58], rax
0x140012db4  lea     rcx, _TraceLoggingMetadata
0x140012dbb  mov     rax, cs:qword_140009480
0x140012dc2  lea     rdx, [rsp+0C8h+EventDescriptor]; EventDescriptor
0x140012dc7  mov     [rsp+0C8h+var_90], rax
0x140012dcc  xor     r9d, r9d; RelatedActivityId
0x140012dcf  lea     rax, [rsp+0C8h+var_90]
0x140012dd4  mov     [rsp+0C8h+var_40], 8
0x140012de0  mov     [rsp+0C8h+var_48], rax
0x140012de8  xor     r8d, r8d; ActivityId
0x140012deb  movzx   eax, cs:word_14000743E
0x140012df2  mov     dword ptr [rsp+0C8h+EventDescriptor.Level], eax
0x140012df6  mov     rax, cs:off_140009058
0x140012dfd  mov     [rsp+0C8h+var_78.Ptr], rax
0x140012e02  mov     dword ptr [rsp+0C8h+EventDescriptor.Id], 0B000000h
0x140012e0a  movzx   eax, word ptr [rax]
0x140012e0d  mov     [rsp+0C8h+var_78.Size], eax
0x140012e11  lea     rax, unk_140007448
0x140012e18  mov     [rsp+0C8h+var_68], rax
0x140012e1d  lea     rax, _TraceLoggingMetadataEnd
0x140012e24  sub     eax, ecx
0x140012e26  mov     dword ptr [rsp+0C8h+var_78.0Ch], 2
0x140012e2e  mov     [rsp+0C8h+var_60], 32h ; '2'
0x140012e36  mov     [rsp+0C8h+var_5C], 1
0x140012e3e  mov     [rsp+0C8h+var_98], eax
0x140012e42  mov     eax, [rsp+0C8h+var_98]
0x140012e46  mov     rcx, cs:RegHandle; RegHandle
0x140012e4d  lea     rax, [rsp+0C8h+var_78]
0x140012e52  mov     [rsp+0C8h+UserData], rax; UserData
0x140012e57  mov     [rsp+0C8h+UserDataCount], 4; UserDataCount
0x140012e5f  call    cs:__imp_EtwWriteTransfer
0x140012e66  nop     dword ptr [rax+rax+00h]
0x140012e6b  mov     al, 1
0x140012e6d  mov     rcx, [rsp+0C8h+var_38]
0x140012e75  xor     rcx, rsp; StackCookie
0x140012e78  call    __security_check_cookie
0x140012e7d  mov     rbx, [rsp+0C8h+arg_0]
0x140012e85  add     rsp, 0A0h
0x140012e8c  pop     r15
0x140012e8e  pop     r14
0x140012e90  pop     rdi
0x140012e91  pop     rsi
0x140012e92  pop     rbp
0x140012e93  retn
```
