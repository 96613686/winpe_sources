# TdiPortToServiceClassIdCallback

- ea: `0x14000a380`
- end: `0x14000a5e4`
- name: `TdiPortToServiceClassIdCallback`
- size: `612`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006f68`
- `0x1400079c0`

## callees

- `0x140003cb4`
- `0x140006bc0`
- `0x140007350`
- `0x1400077cc`
- `0x14000a380`
- `0x14000bb4c`
- `0x140018d08`
- `0x14001a4f8`
- `0x14001ea34`
- `0x14001f210`
- `0x14001fa68`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a5b1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a5b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5c5`

## string_xrefs

- `0x14000a53c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x14000a453`: `ServicesAllowedList`

## pseudocode

```c
void __fastcall TdiPortToServiceClassIdCallback(int a1, char *a2, __int64 a3, unsigned int a4)
{
  int v7; // eax
  __int64 v8; // rcx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  struct _DEVICE_OBJECT *v11; // rcx
  unsigned int v12; // edi
  __int128 v13; // xmm6
  __int128 *v14; // rbp
  char v15; // di
  const wchar_t *v16; // r9
  int v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _OWORD v22[2]; // [rsp+40h] [rbp-68h] BYREF

  v7 = a1;
  if ( a1 < 0 )
  {
    while ( (v7 == -1073741667 || v7 == -1073741275) && a2[37] )
    {
      v8 = *(_QWORD *)a2;
      v9 = *(_OWORD *)(a2 + 8);
      a2[37] = 0;
      v10 = *(_OWORD *)(a2 + 20);
      v11 = *(struct _DEVICE_OBJECT **)(v8 + 88);
      v22[0] = v9;
      *(_OWORD *)((char *)v22 + 12) = v10;
      v7 = BthPortToServiceClassIdList(v11, (__int64)a2);
      if ( v7 >= 0 )
        return;
    }
    goto LABEL_25;
  }
  v12 = 0;
  v13 = 0;
  if ( a4 )
  {
    while ( 1 )
    {
      v14 = (__int128 *)(a3 + 16LL * v12);
      v13 = *v14;
      if ( !(unsigned int)BthServiceAllowedByPolicy(v14) )
        break;
      if ( ++v12 >= a4 )
        goto LABEL_10;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF__guid_(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)a2, a3, 50);
    v15 = 0;
  }
  else
  {
LABEL_10:
    v15 = 1;
  }
  v22[0] = v13;
  if ( (Microsoft_Windows_Bluetooth_PolicyEnableBits & 1) != 0 )
  {
    v16 = L"accepted";
    if ( !v15 )
      v16 = L"blocked";
    v17 = McTemplateK0zjxzz_EtwWriteTransfer(
            a1,
            (_DWORD)a2,
            a3,
            (_DWORD)v16,
            (__int64)v22,
            *((_QWORD *)a2 + 1),
            (__int64)L"Bluetooth",
            (__int64)L"ServicesAllowedList");
    if ( v17 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        15,
        51,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v17);
  }
  if ( !v15 )
  {
    v7 = -1073740959;
LABEL_25:
    if ( v7 < 0 )
    {
      if ( a2[36] )
        ChannelCompleteAccept(*((_QWORD *)a2 + 5), 0, 0, (unsigned int)v7);
      else
        TdiCompleteConnect(*((_QWORD *)a2 + 7), (unsigned int)v7);
    }
    goto LABEL_29;
  }
  if ( a2[36] )
    TdiClientAccept(*((_QWORD *)a2 + 5), *((_QWORD *)a2 + 6));
  else
    TdiConnectToPort(*((_QWORD *)a2 + 7));
LABEL_29:
  v19 = *((_QWORD *)a2 + 6);
  if ( v19 )
    RefObj_ReleaseEx(v19 + 24, 1145652818, 1126, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  v20 = *((_QWORD *)a2 + 7);
  if ( v20 )
    RefObj_ReleaseEx(v20 + 24, 1145652818, 1130, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  v21 = *((_QWORD *)a2 + 5);
  if ( v21 )
    RefObj_ReleaseEx(v21 + 24, 1145652818, 1134, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(*(_QWORD *)a2 + 40LL), TdiPortToServiceClassIdCallback, 0x20u);
  ExFreePoolWithTag(a2, 0x6D636652u);
}

```

## disassembly

```asm
0x14000a380  push    rbx
0x14000a382  push    rbp
0x14000a383  push    rsi
0x14000a384  push    rdi
0x14000a385  push    r12
0x14000a387  push    r14
0x14000a389  sub     rsp, 78h
0x14000a38d  movaps  [rsp+0A8h+var_48], xmm6
0x14000a392  mov     esi, r9d
0x14000a395  mov     r14, r8
0x14000a398  mov     rbx, rdx
0x14000a39b  mov     eax, ecx
0x14000a39d  test    ecx, ecx
0x14000a39f  jns     short loc_14000A3F9
0x14000a3a1  cmp     eax, 0C000009Dh
0x14000a3a6  jz      short loc_14000A3B3
0x14000a3a8  cmp     eax, 0C0000225h
0x14000a3ad  jnz     loc_14000A510
0x14000a3b3  cmp     byte ptr [rbx+25h], 0
0x14000a3b7  jz      loc_14000A510
0x14000a3bd  mov     rcx, [rbx]
0x14000a3c0  lea     r8, [rsp+0A8h+var_68]
0x14000a3c5  movups  xmm0, xmmword ptr [rbx+8]
0x14000a3c9  mov     byte ptr [rbx+25h], 0
0x14000a3cd  xor     r9d, r9d
0x14000a3d0  movups  xmm1, xmmword ptr [rbx+14h]
0x14000a3d4  mov     rdx, [rcx+50h]
0x14000a3d8  mov     rcx, [rcx+58h]; DeviceObject
0x14000a3dc  movaps  xmmword ptr [rsp+0A8h+var_68], xmm0
0x14000a3e1  movups  xmmword ptr [rsp+0A8h+var_68+0Ch], xmm1
0x14000a3e6  mov     [rsp+0A8h+var_88], rbx; __int64
0x14000a3eb  call    BthPortToServiceClassIdList
0x14000a3f0  test    eax, eax
0x14000a3f2  js      short loc_14000A3A1
0x14000a3f4  jmp     loc_14000A5D1
0x14000a3f9  xor     edi, edi
0x14000a3fb  lea     r12, WPP_RECORDER_INITIALIZED
0x14000a402  xorps   xmm6, xmm6
0x14000a405  test    esi, esi
0x14000a407  jz      short loc_14000A42C
0x14000a409  mov     ebp, edi
0x14000a40b  shl     rbp, 4
0x14000a40f  add     rbp, r14
0x14000a412  mov     rcx, rbp
0x14000a415  movups  xmm6, xmmword ptr [rbp+0]
0x14000a419  call    BthServiceAllowedByPolicy
0x14000a41e  test    eax, eax
0x14000a420  jz      loc_14000A4D4
0x14000a426  inc     edi
0x14000a428  cmp     edi, esi
0x14000a42a  jb      short loc_14000A409
0x14000a42c  mov     dil, 1
0x14000a42f  test    cs:Microsoft_Windows_Bluetooth_PolicyEnableBits, 1
0x14000a436  movdqa  xmmword ptr [rsp+0A8h+var_68], xmm6
0x14000a43c  jz      short loc_14000A4BA
0x14000a43e  lea     rax, aBlocked; "blocked"
0x14000a445  test    dil, dil
0x14000a448  lea     r9, aAccepted; "accepted"
0x14000a44f  cmovz   r9, rax
0x14000a453  lea     rax, aServicesallowe; "ServicesAllowedList"
0x14000a45a  mov     [rsp+0A8h+var_70], rax
0x14000a45f  lea     rax, aBluetooth; "Bluetooth"
0x14000a466  mov     [rsp+0A8h+var_78], rax
0x14000a46b  mov     rax, [rbx+8]
0x14000a46f  mov     [rsp+0A8h+var_80], rax
0x14000a474  lea     rax, [rsp+0A8h+var_68]
0x14000a479  mov     [rsp+0A8h+var_88], rax
0x14000a47e  call    McTemplateK0zjxzz_EtwWriteTransfer
0x14000a483  test    eax, eax
0x14000a485  jns     short loc_14000A4BA
0x14000a487  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a48e  jz      short loc_14000A4BA
0x14000a490  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a497  mov     r9d, 33h ; '3'
0x14000a49d  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000a4a1  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000a4a8  mov     [rsp+0A8h+var_88], rax
0x14000a4ad  mov     rcx, [rcx+40h]
0x14000a4b1  lea     r8d, [r9-24h]
0x14000a4b5  call    WPP_RECORDER_SF_d
0x14000a4ba  test    dil, dil
0x14000a4bd  jz      short loc_14000A50B
0x14000a4bf  cmp     byte ptr [rbx+24h], 0
0x14000a4c3  jz      short loc_14000A500
0x14000a4c5  mov     rdx, [rbx+30h]
0x14000a4c9  mov     rcx, [rbx+28h]
0x14000a4cd  call    TdiClientAccept
0x14000a4d2  jmp     short loc_14000A538
0x14000a4d4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000a4db  jz      short loc_14000A4F8
0x14000a4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4e4  mov     r9d, 32h ; '2'
0x14000a4ea  mov     [rsp+0A8h+var_80], rbp
0x14000a4ef  mov     rcx, [rcx+40h]
0x14000a4f3  call    WPP_RECORDER_SF__guid_
0x14000a4f8  xor     dil, dil
0x14000a4fb  jmp     loc_14000A42F
0x14000a500  mov     rcx, [rbx+38h]
0x14000a504  call    TdiConnectToPort
0x14000a509  jmp     short loc_14000A538
0x14000a50b  mov     eax, 0C0000361h
0x14000a510  test    eax, eax
0x14000a512  jns     short loc_14000A538
0x14000a514  cmp     byte ptr [rbx+24h], 0
0x14000a518  jz      short loc_14000A52D
0x14000a51a  mov     rcx, [rbx+28h]
0x14000a51e  mov     r9d, eax
0x14000a521  xor     r8d, r8d
0x14000a524  xor     edx, edx
0x14000a526  call    ChannelCompleteAccept
0x14000a52b  jmp     short loc_14000A538
0x14000a52d  mov     rcx, [rbx+38h]
0x14000a531  mov     edx, eax
0x14000a533  call    TdiCompleteConnect
0x14000a538  mov     rcx, [rbx+30h]
0x14000a53c  lea     rdi, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000a543  mov     esi, 44494652h
0x14000a548  test    rcx, rcx
0x14000a54b  jz      short loc_14000A561
0x14000a54d  add     rcx, 18h
0x14000a551  mov     r9, rdi
0x14000a554  mov     r8d, 466h
0x14000a55a  mov     edx, esi
0x14000a55c  call    RefObj_ReleaseEx
0x14000a561  mov     rcx, [rbx+38h]
0x14000a565  test    rcx, rcx
0x14000a568  jz      short loc_14000A57F
0x14000a56a  add     rcx, 18h
0x14000a56e  mov     r9, rdi
0x14000a571  mov     r8d, 46Ah
0x14000a577  mov     rdx, rsi
0x14000a57a  call    RefObj_ReleaseEx
0x14000a57f  mov     rcx, [rbx+28h]
0x14000a583  test    rcx, rcx
0x14000a586  jz      short loc_14000A59D
0x14000a588  add     rcx, 18h
0x14000a58c  mov     r9, rdi
0x14000a58f  mov     r8d, 46Eh
0x14000a595  mov     rdx, rsi
0x14000a598  call    RefObj_ReleaseEx
0x14000a59d  mov     rcx, [rbx]
0x14000a5a0  lea     rdx, TdiPortToServiceClassIdCallback; Tag
0x14000a5a7  add     rcx, 28h ; '('; RemoveLock
0x14000a5ab  mov     r8d, 20h ; ' '; RemlockSize
0x14000a5b1  call    cs:__imp_IoReleaseRemoveLockEx
0x14000a5b8  nop     dword ptr [rax+rax+00h]
0x14000a5bd  mov     edx, 6D636652h; Tag
0x14000a5c2  mov     rcx, rbx; P
0x14000a5c5  call    cs:__imp_ExFreePoolWithTag
0x14000a5cc  nop     dword ptr [rax+rax+00h]
0x14000a5d1  movaps  xmm6, [rsp+0A8h+var_48]
0x14000a5d6  add     rsp, 78h
0x14000a5da  pop     r14
0x14000a5dc  pop     r12
0x14000a5de  pop     rdi
0x14000a5df  pop     rsi
0x14000a5e0  pop     rbp
0x14000a5e1  pop     rbx
0x14000a5e2  retn
```
