# CSyncMLCmdReplace::BatchUpItemExecution(IConfigManager2 *,CSyncMLItem *)

- ea: `0x18000bc70`
- end: `0x18000bf52`
- name: `?BatchUpItemExecution@CSyncMLCmdReplace@@EEAAJPEAUIConfigManager2@@PEAVCSyncMLItem@@@Z`
- size: `738`
- prototype: `int(CSyncMLCmdReplace *__hidden this, struct IConfigManager2 *, struct CSyncMLItem *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000bc70`
- `0x18000e940`
- `0x180014330`
- `0x1800212c8`
- `0x18002164c`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bf2b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bf2b`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdReplace::BatchUpItemExecution(
        CSyncMLCmdReplace *this,
        struct IConfigManager2 *a2,
        struct CSyncMLItem *a3)
{
  __int64 v5; // rcx
  struct IConfigManager2URI *v7; // rsi
  int v8; // ebx
  __int64 v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r15
  CSyncMLCmdReplace *v12; // rcx
  int v13; // eax
  struct IConfigNode *v14; // rdx
  unsigned int v16; // [rsp+38h] [rbp-49h] BYREF
  int i; // [rsp+3Ch] [rbp-45h] BYREF
  struct IConfigNode *v18; // [rsp+40h] [rbp-41h] BYREF
  int v19; // [rsp+48h] [rbp-39h] BYREF
  int v20; // [rsp+4Ch] [rbp-35h] BYREF
  int v21; // [rsp+50h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-19h] BYREF
  int *v24; // [rsp+78h] [rbp-9h]
  int v25; // [rsp+80h] [rbp-1h]
  int v26; // [rsp+84h] [rbp+3h]
  int *p_i; // [rsp+88h] [rbp+7h]
  __int64 v28; // [rsp+90h] [rbp+Fh]

  v5 = *((_QWORD *)a3 + 9);
  v21 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v7 = (struct IConfigManager2URI *)*((_QWORD *)a3 + 9);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IConfigManager2 *, _QWORD, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
           a2,
           *((_QWORD *)a3 + 9),
           &v18);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v18 + 224LL))(v18, &v19);
      if ( v8 >= 0 )
      {
        v9 = *((_QWORD *)this + 10);
        v10 = 0;
        v16 = 0;
        for ( i = -1; v10 < *(_DWORD *)(v9 + 248); ++v10 )
        {
          v11 = 8LL * v10;
          if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v11 + *(_QWORD *)(v9 + 296)) + 136LL))(
                 *(_QWORD *)(v11 + *(_QWORD *)(v9 + 296)),
                 &v16) < 0
            || (*(int (__fastcall **)(_QWORD, struct IConfigManager2URI *, _QWORD, int *))(**(_QWORD **)(v11 + *(_QWORD *)(v9 + 296))
                                                                                         + 112LL))(
                 *(_QWORD *)(v11 + *(_QWORD *)(v9 + 296)),
                 v7,
                 0,
                 &i) < 0 )
          {
            break;
          }
          if ( v16 - 1 == i )
          {
            if ( v19 )
              break;
            v8 = -2046820350;
            goto LABEL_21;
          }
        }
        v8 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v18 + 144LL))(v18, &v21);
        if ( v8 >= 0 )
        {
          v13 = *((_DWORD *)a3 + 25) == 15
              ? CSyncMLCmdReplace::ReplaceNodeValue(v12, a3, v18, v19)
              : CSyncMLCmdReplace::ReplaceNodeProperty(v12, a3, v18, v7);
          v8 = v13;
          if ( v13 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v18 + 144LL))(v18, &v20);
            if ( v8 >= 0 )
            {
              v14 = v18;
              *((_DWORD *)a3 + 10) = v20 - v21;
              v8 = CSyncMLItem::SetCfgNode(a3, v14, 0);
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2102788095;
  }
LABEL_21:
  if ( v18 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    i = v8;
    p_i = &i;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v28 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v24 = &dword_180037264;
    UserData.Reserved = 2;
    v25 = 33;
    v26 = 1;
    v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bc70  mov     r11, rsp
0x18000bc73  push    rbp
0x18000bc74  push    rbx
0x18000bc75  push    r12
0x18000bc77  lea     rbp, [r11-5Fh]
0x18000bc7b  sub     rsp, 0C0h
0x18000bc82  mov     rax, cs:__security_cookie
0x18000bc89  xor     rax, rsp
0x18000bc8c  mov     [rbp+57h+var_40], rax
0x18000bc90  xor     r12d, r12d
0x18000bc93  mov     [r11-20h], rsi
0x18000bc97  mov     [r11-28h], rdi
0x18000bc9b  mov     rbx, rdx
0x18000bc9e  mov     rdi, rcx
0x18000bca1  mov     [r11-30h], r14
0x18000bca5  mov     rcx, [r8+48h]
0x18000bca9  mov     r14, r8
0x18000bcac  mov     [rbp+57h+var_88], r12d
0x18000bcb0  mov     [rbp+57h+var_8C], r12d
0x18000bcb4  mov     [rbp+57h+var_90], r12d
0x18000bcb8  mov     [rbp+57h+var_98], r12
0x18000bcbc  test    rcx, rcx
0x18000bcbf  jz      short loc_18000BCCD
0x18000bcc1  mov     rax, [rcx]
0x18000bcc4  mov     rax, [rax+8]
0x18000bcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bccd  mov     rsi, [r14+48h]
0x18000bcd1  test    rsi, rsi
0x18000bcd4  jnz     short loc_18000BCE0
0x18000bcd6  mov     ebx, 82AA0001h
0x18000bcdb  jmp     loc_18000BE46
0x18000bce0  mov     rax, [rbx]
0x18000bce3  lea     r8, [rbp+57h+var_98]
0x18000bce7  mov     rdx, rsi
0x18000bcea  mov     rcx, rbx
0x18000bced  mov     rax, [rax+58h]
0x18000bcf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf6  mov     ebx, eax
0x18000bcf8  test    eax, eax
0x18000bcfa  js      loc_18000BE46
0x18000bd00  mov     rcx, [rbp+57h+var_98]
0x18000bd04  lea     rdx, [rbp+57h+var_90]
0x18000bd08  mov     rax, [rcx]
0x18000bd0b  mov     rax, [rax+0E0h]
0x18000bd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd17  mov     ebx, eax
0x18000bd19  test    eax, eax
0x18000bd1b  js      loc_18000BE46
0x18000bd21  mov     rdi, [rdi+50h]
0x18000bd25  mov     ebx, r12d
0x18000bd28  mov     [rsp+0D0h+var_30], r15
0x18000bd30  mov     [rbp+57h+var_A0], r12d
0x18000bd34  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x18000bd3b  cmp     [rdi+0F8h], r12d
0x18000bd42  jbe     short loc_18000BDB5
0x18000bd44  nop     dword ptr [rax+00h]
0x18000bd48  nop     dword ptr [rax+rax+00000000h]
0x18000bd50  mov     eax, ebx
0x18000bd52  lea     rdx, [rbp+57h+var_A0]
0x18000bd56  lea     r15, ds:0[rax*8]
0x18000bd5e  mov     rax, [rdi+128h]
0x18000bd65  mov     rcx, [r15+rax]
0x18000bd69  mov     rax, [rcx]
0x18000bd6c  mov     rax, [rax+88h]
0x18000bd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd78  test    eax, eax
0x18000bd7a  js      short loc_18000BDB5
0x18000bd7c  mov     rax, [rdi+128h]
0x18000bd83  lea     r9, [rbp+57h+var_9C]
0x18000bd87  xor     r8d, r8d
0x18000bd8a  mov     rdx, rsi
0x18000bd8d  mov     rcx, [r15+rax]
0x18000bd91  mov     rax, [rcx]
0x18000bd94  mov     rax, [rax+70h]
0x18000bd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd9d  test    eax, eax
0x18000bd9f  js      short loc_18000BDB5
0x18000bda1  mov     eax, [rbp+57h+var_A0]
0x18000bda4  dec     eax
0x18000bda6  cmp     eax, [rbp+57h+var_9C]
0x18000bda9  jz      short loc_18000BDEB
0x18000bdab  inc     ebx
0x18000bdad  cmp     ebx, [rdi+0F8h]
0x18000bdb3  jb      short loc_18000BD50
0x18000bdb5  mov     rcx, [rbp+57h+var_98]
0x18000bdb9  lea     rdx, [rbp+57h+var_88]
0x18000bdbd  mov     rax, [rcx]
0x18000bdc0  mov     rax, [rax+90h]
0x18000bdc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdcc  mov     ebx, eax
0x18000bdce  test    eax, eax
0x18000bdd0  js      short loc_18000BE3E
0x18000bdd2  cmp     dword ptr [r14+64h], 0Fh
0x18000bdd7  mov     rdx, r14; struct CSyncMLItem *
0x18000bdda  mov     r8, [rbp+57h+var_98]; struct IConfigNode *
0x18000bdde  jnz     short loc_18000BDF8
0x18000bde0  mov     r9d, [rbp+57h+var_90]; int
0x18000bde4  call    ?ReplaceNodeValue@CSyncMLCmdReplace@@AEBAJPEAVCSyncMLItem@@PEAUIConfigNode@@H@Z; CSyncMLCmdReplace::ReplaceNodeValue(CSyncMLItem *,IConfigNode *,int)
0x18000bde9  jmp     short loc_18000BE00
0x18000bdeb  cmp     [rbp+57h+var_90], r12d
0x18000bdef  jnz     short loc_18000BDB5
0x18000bdf1  mov     ebx, 86000002h
0x18000bdf6  jmp     short loc_18000BE3E
0x18000bdf8  mov     r9, rsi; struct IConfigManager2URI *
0x18000bdfb  call    ?ReplaceNodeProperty@CSyncMLCmdReplace@@AEBAJPEAVCSyncMLItem@@PEAUIConfigNode@@PEAUIConfigManager2URI@@@Z; CSyncMLCmdReplace::ReplaceNodeProperty(CSyncMLItem *,IConfigNode *,IConfigManager2URI *)
0x18000be00  mov     ebx, eax
0x18000be02  test    eax, eax
0x18000be04  js      short loc_18000BE3E
0x18000be06  mov     rcx, [rbp+57h+var_98]
0x18000be0a  lea     rdx, [rbp+57h+var_8C]
0x18000be0e  mov     rax, [rcx]
0x18000be11  mov     rax, [rax+90h]
0x18000be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be1d  mov     ebx, eax
0x18000be1f  test    eax, eax
0x18000be21  js      short loc_18000BE3E
0x18000be23  mov     eax, [rbp+57h+var_8C]
0x18000be26  xor     r8d, r8d; unsigned int
0x18000be29  sub     eax, [rbp+57h+var_88]
0x18000be2c  mov     rcx, r14; this
0x18000be2f  mov     rdx, [rbp+57h+var_98]; struct IConfigNode *
0x18000be33  mov     [r14+28h], eax
0x18000be37  call    ?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z; CSyncMLItem::SetCfgNode(IConfigNode *,ulong)
0x18000be3c  mov     ebx, eax
0x18000be3e  mov     r15, [rsp+0D0h+var_30]
0x18000be46  mov     rcx, [rbp+57h+var_98]
0x18000be4a  mov     r14, [rsp+0D0h+var_28]
0x18000be52  mov     rdi, [rsp+0D0h+var_20]
0x18000be5a  test    rcx, rcx
0x18000be5d  jz      short loc_18000BE6F
0x18000be5f  mov     rax, [rcx]
0x18000be62  mov     rax, [rax+10h]
0x18000be66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6b  mov     [rbp+57h+var_98], r12
0x18000be6f  test    rsi, rsi
0x18000be72  jz      short loc_18000BE83
0x18000be74  mov     rax, [rsi]
0x18000be77  mov     rcx, rsi
0x18000be7a  mov     rax, [rax+10h]
0x18000be7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be83  mov     eax, cs:dword_18003E048
0x18000be89  mov     rsi, [rsp+0B8h]
0x18000be91  cmp     eax, 5
0x18000be94  jbe     loc_18000BF37
0x18000be9a  lea     rax, [rbp+57h+var_9C]
0x18000be9e  mov     [rbp+57h+var_9C], ebx
0x18000bea1  mov     [rbp+57h+var_50], rax
0x18000bea5  lea     rcx, _TraceLoggingMetadata
0x18000beac  movzx   eax, cs:word_18003725A
0x18000beb3  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000beb7  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000beba  xor     r9d, r9d; RelatedActivityId
0x18000bebd  mov     rax, cs:off_18003E050
0x18000bec4  xor     r8d, r8d; ActivityId
0x18000bec7  mov     [rbp+57h+UserData.Ptr], rax
0x18000becb  mov     [rbp+57h+var_48], 4
0x18000bed3  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000beda  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x18000bede  movzx   eax, word ptr [rax]
0x18000bee1  mov     [rbp+57h+UserData.Size], eax
0x18000bee4  lea     rax, dword_180037264
0x18000beeb  mov     [rbp+57h+var_60], rax
0x18000beef  lea     rax, _TraceLoggingMetadataEnd
0x18000bef6  sub     eax, ecx
0x18000bef8  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x18000beff  mov     [rbp+57h+var_58], 21h ; '!'
0x18000bf06  mov     [rbp+57h+var_54], 1
0x18000bf0d  mov     [rbp+57h+var_A0], eax
0x18000bf10  mov     eax, [rbp+57h+var_A0]
0x18000bf13  mov     rcx, cs:RegHandle; RegHandle
0x18000bf1a  lea     rax, [rbp+57h+UserData]
0x18000bf1e  mov     [rsp+28h], rax; UserData
0x18000bf23  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18000bf2b  call    cs:__imp_EventWriteTransfer
0x18000bf32  nop     dword ptr [rax+rax+00h]
0x18000bf37  mov     eax, ebx
0x18000bf39  mov     rcx, [rbp+57h+var_40]
0x18000bf3d  xor     rcx, rsp; StackCookie
0x18000bf40  call    __security_check_cookie
0x18000bf45  add     rsp, 0C0h
0x18000bf4c  pop     r12
0x18000bf4e  pop     rbx
0x18000bf4f  pop     rbp
0x18000bf50  retn
```
