# PsmpFindHostJobContext

- ea: `0x18000a8d0`
- end: `0x18000aaa8`
- name: `PsmpFindHostJobContext`
- size: `472`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005c74`
- `0x18000772c`
- `0x1800078e0`
- `0x180007d40`
- `0x180007fd0`
- `0x180008360`
- `0x180008840`
- `0x180008f10`
- `0x180009630`
- `0x18000aab0`
- `0x18000bc20`
- `0x18000c61c`
- `0x18000e3d0`
- `0x18000f7dc`
- `0x180013b40`
- `0x1800149b0`
- `0x1800188f8`
- `0x18001deb0`
- `0x18002a630`
- `0x18002a7d0`

## callees

- `0x18000a8d0`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000aa9a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000aa9a`

## pseudocode

```c
_QWORD *__fastcall PsmpFindHostJobContext(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r8
  _QWORD *v4; // rbx
  signed __int32 v5; // eax
  signed __int32 v6; // r9d
  signed __int32 v7; // edx
  signed __int32 v9; // r9d
  __int64 v10; // rcx
  char *v11; // rcx
  __int64 v12; // rax
  int v14; // eax
  signed __int32 v15; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v16[3]; // [rsp+34h] [rbp-45h] BYREF
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-19h] BYREF
  __int16 *v20; // [rsp+70h] [rbp-9h]
  int v21; // [rsp+78h] [rbp-1h]
  int v22; // [rsp+7Ch] [rbp+3h]
  signed __int32 *v23; // [rsp+80h] [rbp+7h]
  __int64 v24; // [rsp+88h] [rbp+Fh]
  char *v25; // [rsp+90h] [rbp+17h]
  int v26; // [rsp+98h] [rbp+1Fh]
  int v27; // [rsp+9Ch] [rbp+23h]
  _DWORD *v28; // [rsp+A0h] [rbp+27h]
  __int64 v29; // [rsp+A8h] [rbp+2Fh]
  __int64 *v30; // [rsp+B0h] [rbp+37h]
  __int64 v31; // [rsp+B8h] [rbp+3Fh]

  v3 = *(_QWORD **)(a1 + 6816);
  if ( v3 == (_QWORD *)(a1 + 6816) )
    return 0;
  while ( 1 )
  {
    v4 = v3 - 7;
    if ( *(v3 - 2) == a2 )
    {
      _m_prefetchw(v4 + 9);
      v5 = *((_DWORD *)v4 + 18);
      if ( v5 > 0 )
        break;
    }
LABEL_6:
    v3 = (_QWORD *)*v3;
    if ( v3 == (_QWORD *)(a1 + 6816) )
      return 0;
  }
  while ( 1 )
  {
    v6 = v5;
    v7 = v5;
    v5 = _InterlockedCompareExchange((volatile signed __int32 *)v4 + 18, v5 + 1, v5);
    if ( v5 == v7 )
      break;
    if ( v5 <= 0 )
      goto LABEL_6;
  }
  v9 = v6 + 1;
  if ( (unsigned int)dword_18003F048 > 5 && (qword_18003F058 & 1) != 0 && (qword_18003F060 & 1) == qword_18003F060 )
  {
    v10 = *v4;
    v15 = v9;
    v23 = &v15;
    v24 = 4;
    v11 = (char *)(v10 + 7040);
    if ( v11 )
    {
      v12 = -1;
      while ( *(_WORD *)&v11[2 * v12++ + 2] != 0 )
        ;
      v14 = 2 * v12 + 2;
    }
    else
    {
      v11 = byte_180034900;
      v14 = 2;
    }
    v26 = v14;
    v16[0] = *((_DWORD *)v4 + 4);
    v28 = v16;
    v17 = v4[5];
    v30 = &v17;
    *(_DWORD *)&EventDescriptor.Level = 5;
    v25 = v11;
    UserData.Ptr = (ULONGLONG)off_18003F050;
    v27 = 0;
    v29 = 4;
    v31 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)off_18003F050;
    v20 = word_180039052;
    UserData.Reserved = 2;
    v21 = 55;
    v22 = 1;
    v16[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  return v4;
}

```

## disassembly

```asm
0x18000a8d0  mov     [rsp-8+arg_8], rbx
0x18000a8d5  push    rbp
0x18000a8d6  lea     rbp, [rsp-57h]
0x18000a8db  sub     rsp, 0D0h
0x18000a8e2  mov     rax, cs:__security_cookie
0x18000a8e9  xor     rax, rsp
0x18000a8ec  mov     [rbp+57h+var_10], rax
0x18000a8f0  lea     r10, [rcx+1AA0h]
0x18000a8f7  mov     r11, rdx
0x18000a8fa  mov     r8, [r10]
0x18000a8fd  cmp     r8, r10
0x18000a900  jz      short loc_18000A93D
0x18000a902  cmp     [r8-10h], r11
0x18000a906  lea     rbx, [r8-38h]
0x18000a90a  jnz     short loc_18000A935
0x18000a90c  prefetchw byte ptr [rbx+48h]
0x18000a910  mov     eax, [rbx+48h]
0x18000a913  test    eax, eax
0x18000a915  jle     short loc_18000A935
0x18000a917  nop     word ptr [rax+rax+00000000h]
0x18000a920  mov     r9d, eax
0x18000a923  lea     ecx, [rax+1]
0x18000a926  mov     edx, eax
0x18000a928  lock cmpxchg [rbx+48h], ecx
0x18000a92d  cmp     eax, edx
0x18000a92f  jz      short loc_18000A95C
0x18000a931  test    eax, eax
0x18000a933  jg      short loc_18000A920
0x18000a935  mov     r8, [r8]
0x18000a938  cmp     r8, r10
0x18000a93b  jnz     short loc_18000A902
0x18000a93d  xor     eax, eax
0x18000a93f  mov     rcx, [rbp+57h+var_10]
0x18000a943  xor     rcx, rsp; StackCookie
0x18000a946  call    __security_check_cookie
0x18000a94b  mov     rbx, [rsp+0D0h+arg_8]
0x18000a953  add     rsp, 0D0h
0x18000a95a  pop     rbp
0x18000a95b  retn
0x18000a95c  mov     eax, cs:dword_18003F048
0x18000a962  inc     r9d
0x18000a965  cmp     eax, 5
0x18000a968  jbe     loc_18000AAA0
0x18000a96e  mov     rcx, cs:qword_18003F060
0x18000a975  mov     rax, cs:qword_18003F058
0x18000a97c  test    al, 1
0x18000a97e  jz      loc_18000AAA0
0x18000a984  mov     rax, rcx
0x18000a987  and     eax, 1
0x18000a98a  cmp     rax, rcx
0x18000a98d  jnz     loc_18000AAA0
0x18000a993  mov     rcx, [rbx]
0x18000a996  lea     rax, [rbp+57h+var_A0]
0x18000a99a  xor     edx, edx
0x18000a99c  mov     [rbp+57h+var_A0], r9d
0x18000a9a0  mov     [rbp+57h+var_50], rax
0x18000a9a4  mov     [rbp+57h+var_48], 4
0x18000a9ac  add     rcx, 1B80h
0x18000a9b3  jz      short loc_18000A9D4
0x18000a9b5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a9bc  nop     dword ptr [rax+00h]
0x18000a9c0  cmp     [rcx+rax*2+2], dx
0x18000a9c5  lea     rax, [rax+1]
0x18000a9c9  jnz     short loc_18000A9C0
0x18000a9cb  lea     eax, ds:2[rax*2]
0x18000a9d2  jmp     short loc_18000A9E0
0x18000a9d4  lea     rcx, byte_180034900
0x18000a9db  mov     eax, 2
0x18000a9e0  mov     [rbp+57h+var_38], eax
0x18000a9e3  xor     r9d, r9d; RelatedActivityId
0x18000a9e6  mov     eax, [rbx+10h]
0x18000a9e9  xor     r8d, r8d; ActivityId
0x18000a9ec  mov     [rbp+57h+var_9C], eax
0x18000a9ef  lea     rax, [rbp+57h+var_9C]
0x18000a9f3  mov     [rbp+57h+var_30], rax
0x18000a9f7  mov     rax, [rbx+28h]
0x18000a9fb  mov     [rbp+57h+var_90], rax
0x18000a9ff  lea     rax, [rbp+57h+var_90]
0x18000aa03  mov     [rbp+57h+var_20], rax
0x18000aa07  movzx   eax, cs:word_180039048
0x18000aa0e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000aa11  mov     rax, cs:off_18003F050
0x18000aa18  mov     [rbp+57h+var_40], rcx
0x18000aa1c  lea     rcx, _TraceLoggingMetadataEnd
0x18000aa23  mov     [rbp+57h+var_70.Ptr], rax
0x18000aa27  mov     [rbp+57h+var_34], edx
0x18000aa2a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000aa2e  mov     [rbp+57h+var_28], 4
0x18000aa36  mov     [rbp+57h+var_18], 8
0x18000aa3e  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000aa45  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x18000aa4d  movzx   eax, word ptr [rax]
0x18000aa50  mov     [rbp+57h+var_70.Size], eax
0x18000aa53  lea     rax, word_180039052
0x18000aa5a  mov     [rbp+57h+var_60], rax
0x18000aa5e  lea     rax, _TraceLoggingMetadata
0x18000aa65  sub     ecx, eax
0x18000aa67  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18000aa6e  mov     [rbp+57h+var_58], 37h ; '7'
0x18000aa75  lea     rax, [rbp+57h+var_70]
0x18000aa79  mov     [rbp+57h+var_54], 1
0x18000aa80  mov     [rbp+57h+var_98], ecx
0x18000aa83  mov     ecx, [rbp+57h+var_98]
0x18000aa86  mov     rcx, cs:RegHandle; RegHandle
0x18000aa8d  mov     [rsp+0D0h+UserData], rax; UserData
0x18000aa92  mov     [rsp+0D0h+UserDataCount], 6; UserDataCount
0x18000aa9a  call    cs:__imp_EventWriteTransfer
0x18000aaa0  mov     rax, rbx
0x18000aaa3  jmp     loc_18000A93F
```
