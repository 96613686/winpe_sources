# CSyncMLCmdStatus::StartCmdSpecificElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)

- ea: `0x18000ec70`
- end: `0x18000f215`
- name: `?StartCmdSpecificElement@CSyncMLCmdStatus@@EEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z`
- size: `1445`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ec70`
- `0x18000fee0`
- `0x180014330`
- `0x1800145f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ef4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f1c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ef4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f1c4`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000ed62`
- `DMCmnUtils!InvStrCmpNIW` at `0x18000ed62`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdStatus::StartCmdSpecificElement(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  unsigned int started; // ebx
  unsigned __int64 v10; // rdi
  const unsigned __int16 *v11; // rax
  __int64 v12; // rcx
  int v13; // ebx
  const unsigned __int16 **v14; // r15
  __int64 v15; // rax
  int v17; // ecx
  char *v18; // rax
  _QWORD *v19; // rax
  __int64 v21; // [rsp+48h] [rbp-99h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-91h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+60h] [rbp-81h] BYREF
  char *v24; // [rsp+70h] [rbp-71h]
  int v25; // [rsp+78h] [rbp-69h]
  int v26; // [rsp+7Ch] [rbp-65h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-59h] BYREF
  __int16 *v28; // [rsp+98h] [rbp-49h]
  int v29; // [rsp+A0h] [rbp-41h]
  int v30; // [rsp+A4h] [rbp-3Dh]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+A8h] [rbp-39h]
  __int64 v32; // [rsp+B0h] [rbp-31h]
  const unsigned __int16 *v33; // [rsp+B8h] [rbp-29h]
  int v34; // [rsp+C0h] [rbp-21h]
  int v35; // [rsp+C4h] [rbp-1Dh]

  if ( (*(_DWORD *)(a1 + 168) & 4) != 0 )
  {
    started = CSyncMLMeta::StartElement(*(_QWORD *)(a1 + 176), a2, a3, a4, a5, a6, a7);
    goto LABEL_45;
  }
  if ( a4 && *a4 )
  {
    v10 = a5;
    if ( a5 != 0xFFFFFFFFLL )
      goto LABEL_10;
    v11 = a4;
    v12 = 0x7FFFFFFF;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v12;
    }
    while ( v12 );
    v10 = 0x7FFFFFFF - v12;
    if ( !v12 )
    {
LABEL_15:
      if ( (unsigned int)dword_18003E048 <= 2 )
        goto LABEL_23;
      LODWORD(v21) = a5;
      v15 = -1;
      while ( a4[++v15] != 0 )
        ;
      v33 = a4;
      v34 = 2 * v15 + 2;
      v35 = 0;
      p_EventDescriptor = (EVENT_DESCRIPTOR *)&v21;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      v32 = 4;
      v23.Ptr = 0x20B000000LL;
      *(_QWORD *)&v23.Size = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v28 = (__int16 *)byte_180036569;
      UserData.Reserved = 2;
      v29 = 50;
      v30 = 1;
      *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v23, 0, 0, 4u, &UserData);
LABEL_28:
      started = -2102788095;
    }
    else
    {
LABEL_10:
      v13 = 0;
      while ( 1 )
      {
        v14 = (const unsigned __int16 **)&_ImageBase[4 * v13 + 127256];
        if ( !InvStrCmpNIW(a4, *v14, v10) && !(*v14)[v10] )
          break;
        if ( ++v13 >= 73 )
          goto LABEL_15;
      }
      switch ( v13 )
      {
        case 3:
          if ( a6 != 25 )
            goto LABEL_23;
          v17 = *(_DWORD *)(a1 + 168);
          if ( (v17 & 1) != 0 )
          {
            if ( (unsigned int)dword_18003E048 <= 2 )
              goto LABEL_23;
            *(_DWORD *)&EventDescriptor.Level = 2;
            v23.Ptr = (ULONGLONG)off_18003E050;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0;
            v23.Size = (unsigned __int16)*off_18003E050;
            v18 = (char *)word_180036ABA;
            v25 = 22;
          }
          else
          {
            if ( (v17 & 2) == 0 )
            {
              *(_DWORD *)(a1 + 168) = v17 | 1;
              started = 0;
              break;
            }
            if ( (unsigned int)dword_18003E048 <= 2 )
              goto LABEL_23;
            *(_DWORD *)&EventDescriptor.Level = 2;
            v23.Ptr = (ULONGLONG)off_18003E050;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0;
            v23.Size = (unsigned __int16)*off_18003E050;
            v18 = byte_180036D69;
            v25 = 26;
          }
          goto LABEL_27;
        case 4:
        case 6:
        case 12:
        case 16:
        case 18:
        case 21:
          started = 0;
          if ( a6 != 25 )
            started = -2102788095;
          break;
        case 23:
          if ( a6 != 3 )
          {
            started = -2102788095;
            break;
          }
          if ( (*(_DWORD *)(a1 + 168) & 1) == 0 )
          {
            if ( (unsigned int)dword_18003E048 > 2 )
            {
              *(_DWORD *)&EventDescriptor.Level = 2;
              v23.Ptr = (ULONGLONG)off_18003E050;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              EventDescriptor.Keyword = 0;
              v23.Size = (unsigned __int16)*off_18003E050;
              v18 = byte_18003662D;
              v25 = 33;
LABEL_27:
              v24 = v18;
              v23.Reserved = 2;
              v26 = 1;
              LODWORD(v21) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &v23);
              goto LABEL_28;
            }
            goto LABEL_23;
          }
          if ( *(_QWORD *)(a1 + 176) )
          {
            if ( (unsigned int)dword_18003E048 > 2 )
            {
              *(_DWORD *)&EventDescriptor.Level = 2;
              v23.Ptr = (ULONGLONG)off_18003E050;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              EventDescriptor.Keyword = 0;
              v23.Size = (unsigned __int16)*off_18003E050;
              v18 = byte_180036C65;
              v25 = 25;
              goto LABEL_27;
            }
LABEL_23:
            started = -2102788095;
            break;
          }
          v19 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)&EventDescriptor.Id = v19;
          if ( v19 )
          {
            v19[16] = 0;
            *(_OWORD *)v19 = 0;
            started = 0;
            *((_OWORD *)v19 + 1) = 0;
            *((_OWORD *)v19 + 2) = 0;
            *((_OWORD *)v19 + 3) = 0;
            *((_OWORD *)v19 + 4) = 0;
            *((_OWORD *)v19 + 5) = 0;
            *((_OWORD *)v19 + 6) = 0;
            *((_OWORD *)v19 + 7) = 0;
            *(_DWORD *)(a1 + 168) |= 4u;
            *(_QWORD *)(a1 + 176) = v19;
          }
          else
          {
            *(_QWORD *)(a1 + 176) = 0;
            started = -2147024882;
          }
          break;
        default:
          goto LABEL_23;
      }
    }
  }
  else
  {
    started = -2147024809;
  }
LABEL_45:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Id = started;
    p_EventDescriptor = &EventDescriptor;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v32 = 4;
    v23.Ptr = 0x50B000000LL;
    *(_QWORD *)&v23.Size = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v28 = &word_180037196;
    UserData.Reserved = 2;
    v29 = 36;
    v30 = 1;
    LODWORD(v21) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v23, 0, 0, 3u, &UserData);
  }
  return started;
}

```

## disassembly

```asm
0x18000ec70  mov     r11, rsp
0x18000ec73  push    rbp
0x18000ec74  push    rbx
0x18000ec75  push    r13
0x18000ec77  push    r15
0x18000ec79  lea     rbp, [r11-3Fh]
0x18000ec7d  sub     rsp, 0F8h
0x18000ec84  mov     rax, cs:__security_cookie
0x18000ec8b  xor     rax, rsp
0x18000ec8e  mov     [rbp+37h+var_50], rax
0x18000ec92  mov     [r11-28h], rsi
0x18000ec96  lea     r13, _TraceLoggingMetadataEnd
0x18000ec9d  mov     [r11-30h], rdi
0x18000eca1  xor     r15d, r15d
0x18000eca4  mov     [r11-38h], r12
0x18000eca8  mov     rsi, r9
0x18000ecab  mov     [r11-40h], r14
0x18000ecaf  lea     r9, _TraceLoggingMetadata
0x18000ecb6  mov     r14, rcx
0x18000ecb9  mov     rcx, [rbp+37h+arg_30]
0x18000ecbd  mov     eax, [r14+0A8h]
0x18000ecc4  test    al, 4
0x18000ecc6  jz      short loc_18000ECF8
0x18000ecc8  mov     eax, [rbp+37h+arg_28]
0x18000eccb  mov     r9, rsi
0x18000ecce  mov     [rsp+30h], rcx
0x18000ecd3  mov     rcx, [r14+0B0h]
0x18000ecda  mov     dword ptr [rsp+110h+UserData], eax
0x18000ecde  mov     eax, [rbp+37h+arg_20]
0x18000ece1  mov     [rsp+110h+UserDataCount], eax
0x18000ece5  call    ?StartElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@PEAW42@PEAH@Z; CSyncMLMeta::StartElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,SyncMLElemType *,int *)
0x18000ecea  mov     ebx, eax
0x18000ecec  lea     r9, _TraceLoggingMetadata
0x18000ecf3  jmp     loc_18000F10A
0x18000ecf8  test    rsi, rsi
0x18000ecfb  jz      loc_18000F105
0x18000ed01  cmp     r15w, [rsi]
0x18000ed05  jz      loc_18000F105
0x18000ed0b  mov     r12d, [rbp+37h+arg_20]
0x18000ed0f  mov     eax, 0FFFFFFFFh
0x18000ed14  mov     edi, r12d
0x18000ed17  cmp     r12, rax
0x18000ed1a  jnz     short loc_18000ED42
0x18000ed1c  mov     edi, 7FFFFFFFh
0x18000ed21  mov     rax, rsi
0x18000ed24  mov     ecx, edi
0x18000ed26  cmp     [rax], r15w
0x18000ed2a  jz      short loc_18000ED36
0x18000ed2c  add     rax, 2
0x18000ed30  sub     rcx, 1
0x18000ed34  jnz     short loc_18000ED26
0x18000ed36  sub     rdi, rcx
0x18000ed39  test    rcx, rcx
0x18000ed3c  cmovz   rdi, r15
0x18000ed40  jz      short loc_18000EDBE
0x18000ed42  mov     ebx, r15d
0x18000ed45  mov     eax, ebx
0x18000ed47  lea     rcx, __ImageBase
0x18000ed4e  mov     r8, rdi
0x18000ed51  lea     r15, ds:3E230h[rax*8]
0x18000ed59  add     r15, rcx
0x18000ed5c  mov     rcx, rsi
0x18000ed5f  mov     rdx, [r15]
0x18000ed62  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18000ed69  nop     dword ptr [rax+rax+00h]
0x18000ed6e  test    eax, eax
0x18000ed70  jnz     short loc_18000EDAD
0x18000ed72  mov     rcx, [r15]
0x18000ed75  xor     r15d, r15d
0x18000ed78  cmp     r15w, [rcx+rdi*2]
0x18000ed7d  jnz     short loc_18000EDB0
0x18000ed7f  add     ebx, 0FFFFFFFDh; switch 21 cases
0x18000ed82  cmp     ebx, 14h
0x18000ed85  ja      def_18000EDA7; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000ed8b  lea     rdx, __ImageBase
0x18000ed92  movsxd  rax, ebx
0x18000ed95  movzx   eax, ds:(byte_18000F200 - 180000000h)[rdx+rax]
0x18000ed9d  mov     ecx, ds:(jpt_18000EDA7 - 180000000h)[rdx+rax*4]
0x18000eda4  add     rcx, rdx
0x18000eda7  jmp     rcx; switch jump
0x18000edad  xor     r15d, r15d
0x18000edb0  inc     ebx
0x18000edb2  cmp     ebx, 49h ; 'I'
0x18000edb5  jl      short loc_18000ED45
0x18000edb7  lea     r9, _TraceLoggingMetadata
0x18000edbe  mov     eax, cs:dword_18003E048
0x18000edc4  cmp     eax, 2
0x18000edc7  jbe     def_18000EDA7; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000edcd  mov     dword ptr [rsp+110h+var_D0], r12d
0x18000edd2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000edd9  nop     dword ptr [rax+00000000h]
0x18000ede0  cmp     word ptr [rsi+rax*2+2], 0
0x18000ede6  lea     rax, [rax+1]
0x18000edea  jnz     short loc_18000EDE0
0x18000edec  lea     eax, ds:2[rax*2]
0x18000edf3  mov     [rbp+37h+var_60], rsi
0x18000edf7  mov     [rbp+37h+var_58], eax
0x18000edfa  lea     rdx, [rsp+110h+var_B8]
0x18000edff  lea     rax, [rsp+110h+var_D0]
0x18000ee04  mov     [rbp+37h+var_54], r15d
0x18000ee08  mov     [rbp+37h+var_70], rax
0x18000ee0c  movzx   eax, cs:word_18003655F
0x18000ee13  mov     dword ptr [rbp+37h+var_B8.Ptr+4], eax
0x18000ee16  mov     rax, cs:off_18003E050
0x18000ee1d  mov     [rbp+37h+var_90.Ptr], rax
0x18000ee21  mov     [rbp+37h+var_68], 4
0x18000ee29  mov     dword ptr [rsp+110h+var_B8.Ptr], 0B000000h
0x18000ee31  mov     qword ptr [rbp+37h+var_B8.Size], r15
0x18000ee35  movzx   eax, word ptr [rax]
0x18000ee38  mov     [rbp+37h+var_90.Size], eax
0x18000ee3b  lea     rax, byte_180036569
0x18000ee42  mov     [rbp+37h+var_80], rax
0x18000ee46  mov     rax, r13
0x18000ee49  sub     eax, r9d
0x18000ee4c  mov     dword ptr [rbp+37h+var_90.0Ch], 2
0x18000ee53  mov     [rbp+37h+var_78], 32h ; '2'
0x18000ee5a  mov     [rbp+37h+var_74], 1
0x18000ee61  mov     dword ptr [rsp+110h+EventDescriptor.Id], eax
0x18000ee65  mov     eax, dword ptr [rsp+110h+EventDescriptor.Id]
0x18000ee69  lea     rax, [rbp+37h+var_90]
0x18000ee6d  mov     [rsp+110h+UserData], rax
0x18000ee72  mov     [rsp+110h+UserDataCount], 4
0x18000ee7a  jmp     loc_18000EF41
0x18000ee7f  cmp     [rbp+37h+arg_28], 19h; jumptable 000000018000EDA7 cases 4,6,12,16,18,21
0x18000ee83  lea     r9, _TraceLoggingMetadata
0x18000ee8a  mov     ebx, r15d
0x18000ee8d  mov     eax, 82AA0001h
0x18000ee92  cmovnz  ebx, eax
0x18000ee95  jmp     loc_18000F10A
0x18000ee9a  cmp     [rbp+37h+arg_28], 19h; jumptable 000000018000EDA7 case 3
0x18000ee9e  jz      short loc_18000EEB1
0x18000eea0  mov     ebx, 82AA0001h; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000eea5  lea     r9, _TraceLoggingMetadata
0x18000eeac  jmp     loc_18000F10A
0x18000eeb1  mov     ecx, [r14+0A8h]
0x18000eeb8  test    cl, 1
0x18000eebb  jz      loc_18000EF6B
0x18000eec1  mov     eax, cs:dword_18003E048
0x18000eec7  cmp     eax, 2
0x18000eeca  jbe     short def_18000EDA7; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000eecc  movzx   eax, cs:word_180036AB0
0x18000eed3  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x18000eed7  mov     rax, cs:off_18003E050
0x18000eede  mov     [rsp+110h+var_B8.Ptr], rax
0x18000eee3  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18000eeeb  mov     [rsp+110h+EventDescriptor.Keyword], r15
0x18000eef0  movzx   eax, word ptr [rax]
0x18000eef3  mov     [rbp+37h+var_B8.Size], eax
0x18000eef6  lea     rax, word_180036ABA
0x18000eefd  mov     [rbp+37h+var_A0], 16h
0x18000ef04  mov     [rbp+37h+var_A8], rax
0x18000ef08  lea     rcx, _TraceLoggingMetadata
0x18000ef0f  mov     rax, r13
0x18000ef12  mov     dword ptr [rbp+37h+var_B8.0Ch], 2
0x18000ef19  sub     eax, ecx
0x18000ef1b  mov     [rbp+37h+var_9C], 1
0x18000ef22  mov     dword ptr [rsp+110h+var_D0], eax
0x18000ef26  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x18000ef2b  mov     eax, dword ptr [rsp+110h+var_D0]
0x18000ef2f  lea     rax, [rsp+110h+var_B8]
0x18000ef34  mov     [rsp+110h+UserData], rax; UserData
0x18000ef39  mov     [rsp+110h+UserDataCount], 2; UserDataCount
0x18000ef41  mov     rcx, cs:RegHandle; RegHandle
0x18000ef48  xor     r9d, r9d; RelatedActivityId
0x18000ef4b  xor     r8d, r8d; ActivityId
0x18000ef4e  call    cs:__imp_EventWriteTransfer
0x18000ef55  nop     dword ptr [rax+rax+00h]
0x18000ef5a  lea     r9, _TraceLoggingMetadata
0x18000ef61  mov     ebx, 82AA0001h
0x18000ef66  jmp     loc_18000F10A
0x18000ef6b  test    cl, 2
0x18000ef6e  jz      short loc_18000EFBC
0x18000ef70  mov     eax, cs:dword_18003E048
0x18000ef76  cmp     eax, 2
0x18000ef79  jbe     def_18000EDA7; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000ef7f  movzx   eax, cs:word_180036D5F
0x18000ef86  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x18000ef8a  mov     rax, cs:off_18003E050
0x18000ef91  mov     [rsp+110h+var_B8.Ptr], rax
0x18000ef96  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18000ef9e  mov     [rsp+110h+EventDescriptor.Keyword], r15
0x18000efa3  movzx   eax, word ptr [rax]
0x18000efa6  mov     [rbp+37h+var_B8.Size], eax
0x18000efa9  lea     rax, byte_180036D69
0x18000efb0  mov     [rbp+37h+var_A0], 1Ah
0x18000efb7  jmp     loc_18000EF04
0x18000efbc  or      ecx, 1
0x18000efbf  lea     r9, _TraceLoggingMetadata
0x18000efc6  mov     [r14+0A8h], ecx
0x18000efcd  mov     ebx, r15d
0x18000efd0  jmp     loc_18000F10A
0x18000efd5  cmp     [rbp+37h+arg_28], 3; jumptable 000000018000EDA7 case 23
0x18000efd9  jz      short loc_18000EFEC
0x18000efdb  mov     ebx, 82AA0001h
0x18000efe0  lea     r9, _TraceLoggingMetadata
0x18000efe7  jmp     loc_18000F10A
0x18000efec  mov     eax, [r14+0A8h]
0x18000eff3  test    al, 1
0x18000eff5  jnz     short loc_18000F043
0x18000eff7  mov     eax, cs:dword_18003E048
0x18000effd  cmp     eax, 2
0x18000f000  jbe     def_18000EDA7; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000f006  movzx   eax, cs:word_180036623
0x18000f00d  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x18000f011  mov     rax, cs:off_18003E050
0x18000f018  mov     [rsp+110h+var_B8.Ptr], rax
0x18000f01d  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18000f025  mov     [rsp+110h+EventDescriptor.Keyword], r15
0x18000f02a  movzx   eax, word ptr [rax]
0x18000f02d  mov     [rbp+37h+var_B8.Size], eax
0x18000f030  lea     rax, byte_18003662D
0x18000f037  mov     [rbp+37h+var_A0], 21h ; '!'
0x18000f03e  jmp     loc_18000EF04
0x18000f043  cmp     [r14+0B0h], r15
0x18000f04a  jz      short loc_18000F098
0x18000f04c  mov     eax, cs:dword_18003E048
0x18000f052  cmp     eax, 2
0x18000f055  jbe     def_18000EDA7; jumptable 000000018000EDA7 default case, cases 5,7-11,13-15,17,19,20,22
0x18000f05b  movzx   eax, cs:word_180036C5B
0x18000f062  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x18000f066  mov     rax, cs:off_18003E050
0x18000f06d  mov     [rsp+110h+var_B8.Ptr], rax
0x18000f072  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18000f07a  mov     [rsp+110h+EventDescriptor.Keyword], r15
0x18000f07f  movzx   eax, word ptr [rax]
0x18000f082  mov     [rbp+37h+var_B8.Size], eax
0x18000f085  lea     rax, byte_180036C65
0x18000f08c  mov     [rbp+37h+var_A0], 19h
0x18000f093  jmp     loc_18000EF04
0x18000f098  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f09f  mov     ecx, 88h; unsigned __int64
0x18000f0a4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f0a9  mov     qword ptr [rsp+110h+EventDescriptor.Id], rax
0x18000f0ae  lea     r9, _TraceLoggingMetadata
0x18000f0b5  test    rax, rax
0x18000f0b8  jz      short loc_18000F0F7
0x18000f0ba  mov     [rax+80h], r15
0x18000f0c1  xorps   xmm0, xmm0
0x18000f0c4  movups  xmmword ptr [rax], xmm0
0x18000f0c7  mov     ebx, r15d
0x18000f0ca  movups  xmmword ptr [rax+10h], xmm0
0x18000f0ce  movups  xmmword ptr [rax+20h], xmm0
0x18000f0d2  movups  xmmword ptr [rax+30h], xmm0
0x18000f0d6  movups  xmmword ptr [rax+40h], xmm0
0x18000f0da  movups  xmmword ptr [rax+50h], xmm0
0x18000f0de  movups  xmmword ptr [rax+60h], xmm0
0x18000f0e2  movups  xmmword ptr [rax+70h], xmm0
0x18000f0e6  or      dword ptr [r14+0A8h], 4
0x18000f0ee  mov     [r14+0B0h], rax
0x18000f0f5  jmp     short loc_18000F10A
0x18000f0f7  mov     [r14+0B0h], r15
0x18000f0fe  mov     ebx, 8007000Eh
0x18000f103  jmp     short loc_18000F10A
0x18000f105  mov     ebx, 80070057h
0x18000f10a  mov     eax, cs:dword_18003E048
0x18000f110  mov     r14, [rsp+110h+var_38]
0x18000f118  mov     r12, [rsp+110h+var_30]
0x18000f120  mov     rdi, [rsp+110h+var_28]
0x18000f128  mov     rsi, [rsp+0F0h]
0x18000f130  cmp     eax, 5
0x18000f133  jbe     loc_18000F1D0
0x18000f139  lea     rax, [rsp+110h+EventDescriptor]
0x18000f13e  mov     dword ptr [rsp+110h+EventDescriptor.Id], ebx
0x18000f142  mov     [rbp+37h+var_70], rax
0x18000f146  lea     rdx, [rsp+110h+var_B8]; EventDescriptor
0x18000f14b  movzx   eax, cs:word_18003718C
0x18000f152  sub     r13d, r9d
0x18000f155  mov     dword ptr [rbp+37h+var_B8.Ptr+4], eax
0x18000f158  xor     r9d, r9d; RelatedActivityId
0x18000f15b  mov     rax, cs:off_18003E050
0x18000f162  xor     r8d, r8d; ActivityId
0x18000f165  mov     [rbp+37h+var_90.Ptr], rax
0x18000f169  mov     [rbp+37h+var_68], 4
0x18000f171  mov     dword ptr [rsp+110h+var_B8.Ptr], 0B000000h
0x18000f179  mov     qword ptr [rbp+37h+var_B8.Size], r15
0x18000f17d  movzx   eax, word ptr [rax]
0x18000f180  mov     [rbp+37h+var_90.Size], eax
0x18000f183  lea     rax, word_180037196
0x18000f18a  mov     [rbp+37h+var_80], rax
0x18000f18e  mov     dword ptr [rbp+37h+var_90.0Ch], 2
0x18000f195  mov     [rbp+37h+var_78], 24h ; '$'
0x18000f19c  mov     [rbp+37h+var_74], 1
0x18000f1a3  mov     dword ptr [rsp+110h+var_D0], r13d
0x18000f1a8  mov     eax, dword ptr [rsp+110h+var_D0]
0x18000f1ac  mov     rcx, cs:RegHandle; RegHandle
0x18000f1b3  lea     rax, [rbp+37h+var_90]
0x18000f1b7  mov     [rsp+110h+UserData], rax; UserData
0x18000f1bc  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x18000f1c4  call    cs:__imp_EventWriteTransfer
0x18000f1cb  nop     dword ptr [rax+rax+00h]
0x18000f1d0  mov     eax, ebx
0x18000f1d2  mov     rcx, [rbp+37h+var_50]
0x18000f1d6  xor     rcx, rsp; StackCookie
0x18000f1d9  call    __security_check_cookie
0x18000f1de  add     rsp, 0F8h
0x18000f1e5  pop     r15
0x18000f1e7  pop     r13
0x18000f1e9  pop     rbx
0x18000f1ea  pop     rbp
0x18000f1eb  retn
  ... truncated ...
```
