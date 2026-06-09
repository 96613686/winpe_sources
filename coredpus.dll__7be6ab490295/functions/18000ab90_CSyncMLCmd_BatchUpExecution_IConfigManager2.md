# CSyncMLCmd::BatchUpExecution(IConfigManager2 *)

- ea: `0x18000ab90`
- end: `0x18000ade5`
- name: `?BatchUpExecution@CSyncMLCmd@@UEAAJPEAUIConfigManager2@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(CSyncMLCmd *__hidden this, struct IConfigManager2 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000ab90`
- `0x18000fad0`
- `0x180014330`
- `0x1800216c0`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000adc0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000adc0`

## pseudocode

```c
__int64 __fastcall CSyncMLCmd::BatchUpExecution(CSyncMLCmd *this, struct IConfigManager2 *a2)
{
  int v4; // ebx
  struct CSyncMLCmd **v5; // rdi
  struct CSyncMLCmd **i; // rsi
  __int64 v7; // rbp
  __int64 v8; // r15
  __int64 v9; // rdi
  __int64 v10; // rax
  _DWORD v12[2]; // [rsp+30h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-60h] BYREF
  char *v15; // [rsp+58h] [rbp-50h]
  int v16; // [rsp+60h] [rbp-48h]
  int v17; // [rsp+64h] [rbp-44h]
  _DWORD *v18; // [rsp+68h] [rbp-40h]
  __int64 v19; // [rsp+70h] [rbp-38h]

  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_24;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 40LL) )
  {
    v4 = 0;
    if ( *((int *)this + 15) >= 0 )
      *((_DWORD *)this + 15) = -2102722553;
    v5 = (struct CSyncMLCmd **)*((_QWORD *)this + 4);
    for ( i = (struct CSyncMLCmd **)*((_QWORD *)this + 5); v5 != i; ++v5 )
      CSyncMLCmd::SetCmdBypassResult(*v5);
  }
  else
  {
    v4 = CSyncMLCmd::VerifyDTD(this);
    if ( v4 < 0 )
    {
LABEL_24:
      if ( *((int *)this + 15) >= 0 )
        *((_DWORD *)this + 15) = v4;
      goto LABEL_26;
    }
    v7 = 0;
    v8 = (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3;
    if ( (int)v8 > 0 )
    {
      do
      {
        v9 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7);
        if ( *(int *)(v9 + 88) >= 0 )
        {
          v10 = *(_QWORD *)(v9 + 16);
          if ( (!v10 || *(int *)(v10 + 132) >= 0) && *(int *)(v9 + 92) >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 56LL))(a2);
            if ( v4 < 0 )
              goto LABEL_24;
            v4 = (*(__int64 (__fastcall **)(CSyncMLCmd *, struct IConfigManager2 *, __int64))(*(_QWORD *)this + 64LL))(
                   this,
                   a2,
                   v9);
            if ( v4 < 0
              || (v4 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 64LL))(a2), v4 < 0) )
            {
              if ( *(int *)(v9 + 92) >= 0 )
                *(_DWORD *)(v9 + 92) = v4;
              v4 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 72LL))(a2);
              if ( v4 < 0 )
                goto LABEL_24;
              v4 = 0;
            }
          }
        }
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (int)v7 < (int)v8 );
    }
  }
LABEL_26:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v12[0] = v4;
    v18 = v12;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v19 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v15 = byte_180036A91;
    UserData.Reserved = 2;
    v16 = 29;
    v17 = 1;
    v12[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ab90  mov     r11, rsp
0x18000ab93  push    rbx
0x18000ab94  sub     rsp, 0A0h
0x18000ab9b  mov     rax, cs:__security_cookie
0x18000aba2  xor     rax, rsp
0x18000aba5  mov     [rsp+0A8h+var_30], rax
0x18000abaa  mov     [r11+18h], rbp
0x18000abae  mov     [r11-10h], rsi
0x18000abb2  mov     rsi, rcx
0x18000abb5  mov     [r11-18h], rdi
0x18000abb9  mov     [r11-20h], r14
0x18000abbd  mov     r14, rdx
0x18000abc0  mov     [r11-28h], r15
0x18000abc4  test    rdx, rdx
0x18000abc7  jnz     short loc_18000ABD3
0x18000abc9  mov     ebx, 80004003h
0x18000abce  jmp     loc_18000ACDA
0x18000abd3  mov     rax, [rcx+50h]
0x18000abd7  cmp     dword ptr [rax+28h], 0
0x18000abdb  jz      short loc_18000AC16
0x18000abdd  xor     ebx, ebx
0x18000abdf  cmp     [rcx+3Ch], ebx
0x18000abe2  jl      short loc_18000ABEB
0x18000abe4  mov     dword ptr [rcx+3Ch], 82AB0007h
0x18000abeb  mov     rdi, [rcx+20h]
0x18000abef  mov     rsi, [rcx+28h]
0x18000abf3  cmp     rdi, rsi
0x18000abf6  jz      loc_18000ACE3
0x18000abfc  nop     dword ptr [rax+00h]
0x18000ac00  mov     rcx, [rdi]; struct CSyncMLCmd *
0x18000ac03  call    ?SetCmdBypassResult@CSyncMLCmd@@SAXPEAV1@@Z; CSyncMLCmd::SetCmdBypassResult(CSyncMLCmd *)
0x18000ac08  add     rdi, 8
0x18000ac0c  cmp     rdi, rsi
0x18000ac0f  jnz     short loc_18000AC00
0x18000ac11  jmp     loc_18000ACE3
0x18000ac16  call    ?VerifyDTD@CSyncMLCmd@@IEBAJXZ; CSyncMLCmd::VerifyDTD(void)
0x18000ac1b  mov     ebx, eax
0x18000ac1d  test    eax, eax
0x18000ac1f  js      loc_18000ACDA
0x18000ac25  mov     r15, [rsi+10h]
0x18000ac29  xor     ebp, ebp
0x18000ac2b  sub     r15, [rsi+8]
0x18000ac2f  sar     r15, 3
0x18000ac33  test    r15d, r15d
0x18000ac36  jle     loc_18000ACE3
0x18000ac3c  nop     dword ptr [rax+00h]
0x18000ac40  mov     rax, [rsi+8]
0x18000ac44  mov     rdi, [rax+rbp*8]
0x18000ac48  cmp     dword ptr [rdi+58h], 0
0x18000ac4c  jl      short loc_18000ACCB
0x18000ac4e  mov     rax, [rdi+10h]
0x18000ac52  test    rax, rax
0x18000ac55  jz      short loc_18000AC60
0x18000ac57  cmp     dword ptr [rax+84h], 0
0x18000ac5e  jl      short loc_18000ACCB
0x18000ac60  cmp     dword ptr [rdi+5Ch], 0
0x18000ac64  jl      short loc_18000ACCB
0x18000ac66  mov     rax, [r14]
0x18000ac69  mov     rcx, r14
0x18000ac6c  mov     rax, [rax+38h]
0x18000ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac75  mov     ebx, eax
0x18000ac77  test    eax, eax
0x18000ac79  js      short loc_18000ACDA
0x18000ac7b  mov     rax, [rsi]
0x18000ac7e  mov     r8, rdi
0x18000ac81  mov     rdx, r14
0x18000ac84  mov     rcx, rsi
0x18000ac87  mov     rax, [rax+40h]
0x18000ac8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac90  mov     ebx, eax
0x18000ac92  test    eax, eax
0x18000ac94  js      short loc_18000ACAB
0x18000ac96  mov     rax, [r14]
0x18000ac99  mov     rcx, r14
0x18000ac9c  mov     rax, [rax+40h]
0x18000aca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca5  mov     ebx, eax
0x18000aca7  test    eax, eax
0x18000aca9  jns     short loc_18000ACCB
0x18000acab  cmp     dword ptr [rdi+5Ch], 0
0x18000acaf  jl      short loc_18000ACB4
0x18000acb1  mov     [rdi+5Ch], ebx
0x18000acb4  mov     rax, [r14]
0x18000acb7  mov     rcx, r14
0x18000acba  mov     rax, [rax+48h]
0x18000acbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc3  mov     ebx, eax
0x18000acc5  test    eax, eax
0x18000acc7  js      short loc_18000ACDA
0x18000acc9  xor     ebx, ebx
0x18000accb  inc     ebp
0x18000accd  cmp     ebp, r15d
0x18000acd0  jl      loc_18000AC40
0x18000acd6  test    ebx, ebx
0x18000acd8  jns     short loc_18000ACE3
0x18000acda  cmp     dword ptr [rsi+3Ch], 0
0x18000acde  jl      short loc_18000ACE3
0x18000ace0  mov     [rsi+3Ch], ebx
0x18000ace3  mov     eax, cs:dword_18003E048
0x18000ace9  mov     r15, [rsp+0A8h+var_28]
0x18000acf1  mov     r14, [rsp+0A8h+var_20]
0x18000acf9  mov     rdi, [rsp+0A8h+var_18]
0x18000ad01  mov     rsi, [rsp+0A8h+var_10]
0x18000ad09  mov     rbp, [rsp+0A8h+arg_10]
0x18000ad11  cmp     eax, 5
0x18000ad14  jbe     loc_18000ADCC
0x18000ad1a  lea     rax, [rsp+0A8h+var_78]
0x18000ad1f  mov     [rsp+0A8h+var_78], ebx
0x18000ad23  mov     [rsp+0A8h+var_40], rax
0x18000ad28  lea     rcx, _TraceLoggingMetadata
0x18000ad2f  movzx   eax, cs:word_180036A87
0x18000ad36  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x18000ad3b  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x18000ad3f  xor     r9d, r9d; RelatedActivityId
0x18000ad42  mov     rax, cs:off_18003E050
0x18000ad49  xor     r8d, r8d; ActivityId
0x18000ad4c  mov     [rsp+0A8h+var_60.Ptr], rax
0x18000ad51  mov     [rsp+0A8h+var_38], 4
0x18000ad5a  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x18000ad62  mov     [rsp+0A8h+EventDescriptor.Keyword], 0
0x18000ad6b  movzx   eax, word ptr [rax]
0x18000ad6e  mov     [rsp+0A8h+var_60.Size], eax
0x18000ad72  lea     rax, byte_180036A91
0x18000ad79  mov     [rsp+0A8h+var_50], rax
0x18000ad7e  lea     rax, _TraceLoggingMetadataEnd
0x18000ad85  sub     eax, ecx
0x18000ad87  mov     dword ptr [rsp+0A8h+var_60.0Ch], 2
0x18000ad8f  mov     [rsp+0A8h+var_48], 1Dh
0x18000ad97  mov     [rsp+0A8h+var_44], 1
0x18000ad9f  mov     [rsp+0A8h+var_74], eax
0x18000ada3  mov     eax, [rsp+0A8h+var_74]
0x18000ada7  mov     rcx, cs:RegHandle; RegHandle
0x18000adae  lea     rax, [rsp+0A8h+var_60]
0x18000adb3  mov     [rsp+0A8h+UserData], rax; UserData
0x18000adb8  mov     [rsp+0A8h+UserDataCount], 3; UserDataCount
0x18000adc0  call    cs:__imp_EventWriteTransfer
0x18000adc7  nop     dword ptr [rax+rax+00h]
0x18000adcc  mov     eax, ebx
0x18000adce  mov     rcx, [rsp+0A8h+var_30]
0x18000add3  xor     rcx, rsp; StackCookie
0x18000add6  call    __security_check_cookie
0x18000addb  add     rsp, 0A0h
0x18000ade2  pop     rbx
0x18000ade3  retn
```
