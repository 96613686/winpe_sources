# CSyncMLItem::GetItemExecHresult(long *)

- ea: `0x180003b60`
- end: `0x180003cc8`
- name: `?GetItemExecHresult@CSyncMLItem@@QEAAJPEAJ@Z`
- size: `360`
- prototype: `int(CSyncMLItem *__hidden this, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e490`
- `0x18001fee0`
- `0x180020798`

## callees

- `0x180003b60`
- `0x180009560`
- `0x180014330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003ca3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003ca3`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::GetItemExecHresult(unsigned __int64 this, int *a2)
{
  int v2; // eax
  int ExecutionHresult; // ebp
  unsigned __int64 v5; // rdi
  __int64 v6; // rbx
  struct IConfigNode *v7; // rdx
  _DWORD v9[2]; // [rsp+30h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-50h] BYREF
  __int16 *v12; // [rsp+58h] [rbp-40h]
  int v13; // [rsp+60h] [rbp-38h]
  int v14; // [rsp+64h] [rbp-34h]
  _DWORD *v15; // [rsp+68h] [rbp-30h]
  __int64 v16; // [rsp+70h] [rbp-28h]

  v2 = *(_DWORD *)(this + 96);
  ExecutionHresult = 0;
  v5 = this;
  if ( v2 >= 0 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *(struct IConfigNode **)(v5 + 8 * v6 + 48);
      if ( v7 )
      {
        ExecutionHresult = CSyncMLItem::GetExecutionHresult(
                             (CSyncMLItem *)this,
                             v7,
                             *(_DWORD *)(v5 + 4 * v6 + 32),
                             *(_DWORD *)(v5 + 4 * v6 + 40),
                             a2);
        if ( ExecutionHresult < 0 )
          goto LABEL_10;
        this = (unsigned int)*a2;
        if ( (this & 0x80000000) != 0LL )
          break;
      }
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= 2 )
        goto LABEL_10;
    }
    *(_DWORD *)(v5 + 96) = this;
  }
  else
  {
    *a2 = v2;
  }
LABEL_10:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v9[0] = ExecutionHresult;
    v15 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v16 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v12 = &word_18003635E;
    UserData.Reserved = 2;
    v13 = 31;
    v14 = 1;
    v9[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)ExecutionHresult;
}

```

## disassembly

```asm
0x180003b60  mov     r11, rsp
0x180003b63  push    rbp
0x180003b64  sub     rsp, 90h
0x180003b6b  mov     rax, cs:__security_cookie
0x180003b72  xor     rax, rsp
0x180003b75  mov     [rsp+98h+var_20], rax
0x180003b7a  mov     eax, [rcx+60h]
0x180003b7d  xor     ebp, ebp
0x180003b7f  mov     [r11-10h], rsi
0x180003b83  mov     rsi, rdx
0x180003b86  mov     [r11-18h], rdi
0x180003b8a  mov     rdi, rcx
0x180003b8d  test    eax, eax
0x180003b8f  jns     short loc_180003B95
0x180003b91  mov     [rdx], eax
0x180003b93  jmp     short loc_180003BDE
0x180003b95  mov     [rsp+98h+arg_10], rbx
0x180003b9d  xor     ebx, ebx
0x180003b9f  nop
0x180003ba0  mov     rdx, [rdi+rbx*8+30h]; struct IConfigNode *
0x180003ba5  test    rdx, rdx
0x180003ba8  jz      short loc_180003BCA
0x180003baa  mov     r9d, [rdi+rbx*4+28h]; unsigned int
0x180003baf  mov     r8d, [rdi+rbx*4+20h]; unsigned int
0x180003bb4  mov     qword ptr [rsp+98h+UserDataCount], rsi; int *
0x180003bb9  call    ?GetExecutionHresult@CSyncMLItem@@AEBAJPEAUIConfigNode@@KKPEAJ@Z; CSyncMLItem::GetExecutionHresult(IConfigNode *,ulong,ulong,long *)
0x180003bbe  mov     ebp, eax
0x180003bc0  test    eax, eax
0x180003bc2  js      short loc_180003BD6
0x180003bc4  mov     ecx, [rsi]
0x180003bc6  test    ecx, ecx
0x180003bc8  js      short loc_180003BD3
0x180003bca  inc     ebx
0x180003bcc  cmp     ebx, 2
0x180003bcf  jb      short loc_180003BA0
0x180003bd1  jmp     short loc_180003BD6
0x180003bd3  mov     [rdi+60h], ecx
0x180003bd6  mov     rbx, [rsp+98h+arg_10]
0x180003bde  mov     eax, cs:dword_18003E048
0x180003be4  mov     rdi, [rsp+98h+var_18]
0x180003bec  mov     rsi, [rsp+98h+var_10]
0x180003bf4  cmp     eax, 5
0x180003bf7  jbe     loc_180003CAF
0x180003bfd  lea     rax, [rsp+98h+var_68]
0x180003c02  mov     [rsp+98h+var_68], ebp
0x180003c06  mov     [rsp+98h+var_30], rax
0x180003c0b  lea     rcx, _TraceLoggingMetadata
0x180003c12  movzx   eax, cs:word_180036354
0x180003c19  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x180003c1e  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x180003c22  xor     r9d, r9d; RelatedActivityId
0x180003c25  mov     rax, cs:off_18003E050
0x180003c2c  xor     r8d, r8d; ActivityId
0x180003c2f  mov     [rsp+98h+var_50.Ptr], rax
0x180003c34  mov     [rsp+98h+var_28], 4
0x180003c3d  mov     dword ptr [rsp+98h+EventDescriptor.Id], 0B000000h
0x180003c45  mov     [rsp+98h+EventDescriptor.Keyword], 0
0x180003c4e  movzx   eax, word ptr [rax]
0x180003c51  mov     [rsp+98h+var_50.Size], eax
0x180003c55  lea     rax, word_18003635E
0x180003c5c  mov     [rsp+98h+var_40], rax
0x180003c61  lea     rax, _TraceLoggingMetadataEnd
0x180003c68  sub     eax, ecx
0x180003c6a  mov     dword ptr [rsp+98h+var_50.0Ch], 2
0x180003c72  mov     [rsp+98h+var_38], 1Fh
0x180003c7a  mov     [rsp+98h+var_34], 1
0x180003c82  mov     [rsp+98h+var_64], eax
0x180003c86  mov     eax, [rsp+98h+var_64]
0x180003c8a  mov     rcx, cs:RegHandle; RegHandle
0x180003c91  lea     rax, [rsp+98h+var_50]
0x180003c96  mov     [rsp+98h+UserData], rax; UserData
0x180003c9b  mov     [rsp+98h+UserDataCount], 3; UserDataCount
0x180003ca3  call    cs:__imp_EventWriteTransfer
0x180003caa  nop     dword ptr [rax+rax+00h]
0x180003caf  mov     eax, ebp
0x180003cb1  mov     rcx, [rsp+98h+var_20]
0x180003cb6  xor     rcx, rsp; StackCookie
0x180003cb9  call    __security_check_cookie
0x180003cbe  add     rsp, 90h
0x180003cc5  pop     rbp
0x180003cc6  retn
```
