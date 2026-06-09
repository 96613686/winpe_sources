# CSyncMLCmd::VerifyDTD(void)

- ea: `0x18000fad0`
- end: `0x18000fece`
- name: `?VerifyDTD@CSyncMLCmd@@IEBAJXZ`
- size: `1022`
- prototype: `__int64 __fastcall(CSyncMLCmd *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ab90`
- `0x18000adf0`
- `0x18001e960`
- `0x18001eae0`
- `0x18001ed20`

## callees

- `0x18000fad0`
- `0x180014330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fe01`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fea5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fe01`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fea5`

## pseudocode

```c
__int64 __fastcall CSyncMLCmd::VerifyDTD(CSyncMLCmd *this)
{
  _WORD *v1; // rdx
  unsigned __int64 v2; // rax
  unsigned __int64 v3; // rdx
  __int16 *v4; // rax
  int *v5; // rax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v9; // [rsp+34h] [rbp-4Ch] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  char *v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+60h] [rbp-20h]
  int v14; // [rsp+64h] [rbp-1Ch]
  unsigned int *v15; // [rsp+68h] [rbp-18h]
  __int64 v16; // [rsp+70h] [rbp-10h]

  v1 = (_WORD *)*((_QWORD *)this + 13);
  if ( !v1 || !*v1 )
  {
    if ( (unsigned int)dword_18003E048 <= 2 )
      goto LABEL_27;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v5 = &dword_180036754;
    v13 = 17;
    goto LABEL_26;
  }
  v2 = *((unsigned int *)this + 38);
  v3 = (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3;
  if ( v3 )
  {
    if ( (_DWORD)v2 && v3 < v2 )
    {
      if ( (unsigned int)dword_18003E048 <= 2 )
        goto LABEL_27;
      v8 = *((_DWORD *)this + 38);
      v15 = &v8;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      v16 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v4 = (__int16 *)&byte_180036537;
      v13 = 38;
      goto LABEL_12;
    }
  }
  else if ( (_DWORD)v2 )
  {
    if ( (unsigned int)dword_18003E048 <= 2 )
    {
LABEL_27:
      v6 = -2102788095;
      goto LABEL_28;
    }
    v9 = *((_DWORD *)this + 38);
    v15 = &v9;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v16 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v12 = byte_180036E13;
    UserData.Reserved = 2;
    v13 = 38;
    v14 = 1;
    v8 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_7:
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    goto LABEL_27;
  }
  if ( v3 > *((unsigned int *)this + 39) )
  {
    if ( (unsigned int)dword_18003E048 <= 2 )
      goto LABEL_27;
    v8 = *((_DWORD *)this + 39);
    v15 = &v8;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v16 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v4 = &word_180036CDE;
    v13 = 36;
LABEL_12:
    v12 = (char *)v4;
    UserData.Reserved = 2;
    v14 = 1;
    v9 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 40) && !*((_QWORD *)this + 12) )
  {
    if ( (unsigned int)dword_18003E048 <= 2 )
      goto LABEL_27;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v5 = (int *)&word_180036C0E;
    v13 = 27;
LABEL_26:
    v12 = (char *)v5;
    UserData.Reserved = 2;
    v14 = 1;
    v8 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    goto LABEL_27;
  }
  v6 = 0;
  if ( (__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 3 && !*((_DWORD *)this + 41) )
  {
    if ( (unsigned int)dword_18003E048 <= 2 )
      goto LABEL_27;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v5 = &dword_180036ADC;
    v13 = 28;
    goto LABEL_26;
  }
LABEL_28:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v8 = v6;
    v15 = &v8;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v16 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v12 = byte_180036B2D;
    UserData.Reserved = 2;
    v13 = 22;
    v14 = 1;
    v9 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return v6;
}

```

## disassembly

```asm
0x18000fad0  push    rbp
0x18000fad2  push    rbx
0x18000fad3  push    rsi
0x18000fad4  push    rdi
0x18000fad5  push    r14
0x18000fad7  mov     rbp, rsp
0x18000fada  sub     rsp, 80h
0x18000fae1  mov     rax, cs:__security_cookie
0x18000fae8  xor     rax, rsp
0x18000faeb  mov     [rbp+var_8], rax
0x18000faef  mov     rdx, [rcx+68h]
0x18000faf3  lea     rdi, _TraceLoggingMetadataEnd
0x18000fafa  xor     esi, esi
0x18000fafc  lea     r14, _TraceLoggingMetadata
0x18000fb03  test    rdx, rdx
0x18000fb06  jz      loc_18000FD7E
0x18000fb0c  cmp     si, [rdx]
0x18000fb0f  jz      loc_18000FD7E
0x18000fb15  mov     rdx, [rcx+10h]
0x18000fb19  sub     rdx, [rcx+8]
0x18000fb1d  mov     eax, [rcx+98h]
0x18000fb23  sar     rdx, 3
0x18000fb27  test    rdx, rdx
0x18000fb2a  jnz     loc_18000FBC8
0x18000fb30  test    eax, eax
0x18000fb32  jz      loc_18000FC54
0x18000fb38  mov     eax, cs:dword_18003E048
0x18000fb3e  cmp     eax, 2
0x18000fb41  jbe     loc_18000FE0D
0x18000fb47  mov     eax, [rcx+98h]
0x18000fb4d  mov     [rbp+var_4C], eax
0x18000fb50  lea     rax, [rbp+var_4C]
0x18000fb54  mov     [rbp+var_18], rax
0x18000fb58  movzx   eax, cs:word_180036E09
0x18000fb5f  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fb62  mov     rax, cs:off_18003E050
0x18000fb69  mov     [rbp+var_38.Ptr], rax
0x18000fb6d  mov     [rbp+var_10], 4
0x18000fb75  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fb7c  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fb80  movzx   eax, word ptr [rax]
0x18000fb83  mov     [rbp+var_38.Size], eax
0x18000fb86  lea     rax, byte_180036E13
0x18000fb8d  mov     [rbp+var_28], rax
0x18000fb91  mov     rax, rdi
0x18000fb94  sub     eax, r14d
0x18000fb97  mov     dword ptr [rbp+var_38.0Ch], 2
0x18000fb9e  mov     [rbp+var_20], 26h ; '&'
0x18000fba5  mov     [rbp+var_1C], 1
0x18000fbac  mov     [rbp+var_50], eax
0x18000fbaf  mov     eax, [rbp+var_50]
0x18000fbb2  lea     rax, [rbp+var_38]
0x18000fbb6  mov     [rsp+80h+UserData], rax
0x18000fbbb  mov     [rsp+80h+UserDataCount], 3
0x18000fbc3  jmp     loc_18000FDF0
0x18000fbc8  test    eax, eax
0x18000fbca  jz      loc_18000FC54
0x18000fbd0  cmp     rdx, rax
0x18000fbd3  jnb     short loc_18000FC54
0x18000fbd5  mov     eax, cs:dword_18003E048
0x18000fbdb  cmp     eax, 2
0x18000fbde  jbe     loc_18000FE0D
0x18000fbe4  mov     eax, [rcx+98h]
0x18000fbea  mov     [rbp+var_50], eax
0x18000fbed  lea     rax, [rbp+var_50]
0x18000fbf1  mov     [rbp+var_18], rax
0x18000fbf5  movzx   eax, cs:word_18003652D
0x18000fbfc  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fbff  mov     rax, cs:off_18003E050
0x18000fc06  mov     [rbp+var_38.Ptr], rax
0x18000fc0a  mov     [rbp+var_10], 4
0x18000fc12  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fc19  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fc1d  movzx   eax, word ptr [rax]
0x18000fc20  mov     [rbp+var_38.Size], eax
0x18000fc23  lea     rax, byte_180036537
0x18000fc2a  mov     [rbp+var_20], 26h ; '&'
0x18000fc31  mov     [rbp+var_28], rax
0x18000fc35  mov     rax, rdi
0x18000fc38  sub     eax, r14d
0x18000fc3b  mov     dword ptr [rbp+var_38.0Ch], 2
0x18000fc42  mov     [rbp+var_1C], 1
0x18000fc49  mov     [rbp+var_4C], eax
0x18000fc4c  mov     eax, [rbp+var_4C]
0x18000fc4f  jmp     loc_18000FBB2
0x18000fc54  mov     eax, [rcx+9Ch]
0x18000fc5a  cmp     rdx, rax
0x18000fc5d  jbe     short loc_18000FCC0
0x18000fc5f  mov     eax, cs:dword_18003E048
0x18000fc65  cmp     eax, 2
0x18000fc68  jbe     loc_18000FE0D
0x18000fc6e  mov     eax, [rcx+9Ch]
0x18000fc74  mov     [rbp+var_50], eax
0x18000fc77  lea     rax, [rbp+var_50]
0x18000fc7b  mov     [rbp+var_18], rax
0x18000fc7f  movzx   eax, cs:word_180036CD4
0x18000fc86  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fc89  mov     rax, cs:off_18003E050
0x18000fc90  mov     [rbp+var_38.Ptr], rax
0x18000fc94  mov     [rbp+var_10], 4
0x18000fc9c  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fca3  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fca7  movzx   eax, word ptr [rax]
0x18000fcaa  mov     [rbp+var_38.Size], eax
0x18000fcad  lea     rax, word_180036CDE
0x18000fcb4  mov     [rbp+var_20], 24h ; '$'
0x18000fcbb  jmp     loc_18000FC31
0x18000fcc0  cmp     [rcx+0A0h], esi
0x18000fcc6  jz      short loc_18000FD16
0x18000fcc8  cmp     [rcx+60h], rsi
0x18000fccc  jnz     short loc_18000FD16
0x18000fcce  mov     eax, cs:dword_18003E048
0x18000fcd4  cmp     eax, 2
0x18000fcd7  jbe     loc_18000FE0D
0x18000fcdd  movzx   eax, cs:word_180036C04
0x18000fce4  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fce7  mov     rax, cs:off_18003E050
0x18000fcee  mov     [rbp+var_38.Ptr], rax
0x18000fcf2  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fcf9  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fcfd  movzx   eax, word ptr [rax]
0x18000fd00  mov     [rbp+var_38.Size], eax
0x18000fd03  lea     rax, word_180036C0E
0x18000fd0a  mov     [rbp+var_20], 1Bh
0x18000fd11  jmp     loc_18000FDC1
0x18000fd16  mov     rax, [rcx+28h]
0x18000fd1a  mov     ebx, esi
0x18000fd1c  sub     rax, [rcx+20h]
0x18000fd20  sar     rax, 3
0x18000fd24  test    rax, rax
0x18000fd27  jz      loc_18000FE12
0x18000fd2d  cmp     [rcx+0A4h], ebx
0x18000fd33  jnz     loc_18000FE12
0x18000fd39  mov     eax, cs:dword_18003E048
0x18000fd3f  cmp     eax, 2
0x18000fd42  jbe     loc_18000FE0D
0x18000fd48  movzx   eax, cs:word_180036AD2
0x18000fd4f  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fd52  mov     rax, cs:off_18003E050
0x18000fd59  mov     [rbp+var_38.Ptr], rax
0x18000fd5d  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fd64  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fd68  movzx   eax, word ptr [rax]
0x18000fd6b  mov     [rbp+var_38.Size], eax
0x18000fd6e  lea     rax, dword_180036ADC
0x18000fd75  mov     [rbp+var_20], 1Ch
0x18000fd7c  jmp     short loc_18000FDC1
0x18000fd7e  mov     eax, cs:dword_18003E048
0x18000fd84  cmp     eax, 2
0x18000fd87  jbe     loc_18000FE0D
0x18000fd8d  movzx   eax, cs:word_18003674A
0x18000fd94  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fd97  mov     rax, cs:off_18003E050
0x18000fd9e  mov     [rbp+var_38.Ptr], rax
0x18000fda2  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fda9  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fdad  movzx   eax, word ptr [rax]
0x18000fdb0  mov     [rbp+var_38.Size], eax
0x18000fdb3  lea     rax, dword_180036754
0x18000fdba  mov     [rbp+var_20], 11h
0x18000fdc1  mov     [rbp+var_28], rax
0x18000fdc5  mov     rax, rdi
0x18000fdc8  sub     eax, r14d
0x18000fdcb  mov     dword ptr [rbp+var_38.0Ch], 2
0x18000fdd2  mov     [rbp+var_1C], 1
0x18000fdd9  mov     [rbp+var_50], eax
0x18000fddc  mov     eax, [rbp+var_50]
0x18000fddf  lea     rax, [rbp+var_38]
0x18000fde3  mov     [rsp+80h+UserData], rax; UserData
0x18000fde8  mov     [rsp+80h+UserDataCount], 2; UserDataCount
0x18000fdf0  mov     rcx, cs:RegHandle; RegHandle
0x18000fdf7  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18000fdfb  xor     r9d, r9d; RelatedActivityId
0x18000fdfe  xor     r8d, r8d; ActivityId
0x18000fe01  call    cs:__imp_EventWriteTransfer
0x18000fe08  nop     dword ptr [rax+rax+00h]
0x18000fe0d  mov     ebx, 82AA0001h
0x18000fe12  mov     eax, cs:dword_18003E048
0x18000fe18  cmp     eax, 5
0x18000fe1b  jbe     loc_18000FEB1
0x18000fe21  lea     rax, [rbp+var_50]
0x18000fe25  mov     [rbp+var_50], ebx
0x18000fe28  mov     [rbp+var_18], rax
0x18000fe2c  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18000fe30  movzx   eax, cs:word_180036B23
0x18000fe37  sub     edi, r14d
0x18000fe3a  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18000fe3d  xor     r9d, r9d; RelatedActivityId
0x18000fe40  mov     rax, cs:off_18003E050
0x18000fe47  xor     r8d, r8d; ActivityId
0x18000fe4a  mov     [rbp+var_38.Ptr], rax
0x18000fe4e  mov     [rbp+var_10], 4
0x18000fe56  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18000fe5d  mov     [rbp+EventDescriptor.Keyword], rsi
0x18000fe61  movzx   eax, word ptr [rax]
0x18000fe64  mov     [rbp+var_38.Size], eax
0x18000fe67  lea     rax, byte_180036B2D
0x18000fe6e  mov     [rbp+var_28], rax
0x18000fe72  lea     rax, [rbp+var_38]
0x18000fe76  mov     dword ptr [rbp+var_38.0Ch], 2
0x18000fe7d  mov     [rbp+var_20], 16h
0x18000fe84  mov     [rbp+var_1C], 1
0x18000fe8b  mov     [rsp+80h+UserData], rax; UserData
0x18000fe90  mov     [rbp+var_4C], edi
0x18000fe93  mov     ecx, [rbp+var_4C]
0x18000fe96  mov     rcx, cs:RegHandle; RegHandle
0x18000fe9d  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x18000fea5  call    cs:__imp_EventWriteTransfer
0x18000feac  nop     dword ptr [rax+rax+00h]
0x18000feb1  mov     eax, ebx
0x18000feb3  mov     rcx, [rbp+var_8]
0x18000feb7  xor     rcx, rsp; StackCookie
0x18000feba  call    __security_check_cookie
0x18000febf  add     rsp, 80h
0x18000fec6  pop     r14
0x18000fec8  pop     rdi
0x18000fec9  pop     rsi
0x18000feca  pop     rbx
0x18000fecb  pop     rbp
0x18000fecc  retn
```
