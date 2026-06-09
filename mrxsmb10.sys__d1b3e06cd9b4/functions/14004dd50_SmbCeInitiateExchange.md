# SmbCeInitiateExchange

- ea: `0x14004dd50`
- end: `0x14004e4db`
- name: `SmbCeInitiateExchange`
- size: `1931`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `22`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400017a0`
- `0x14000e3e0`
- `0x1400113f4`
- `0x140029ff0`
- `0x14002cc54`
- `0x14002ff70`
- `0x140034700`
- `0x140034920`
- `0x140034ae0`
- `0x140035968`
- `0x1400367d0`
- `0x140036d40`
- `0x140039420`
- `0x14003bbd0`
- `0x14003c3f8`
- `0x14003e26c`
- `0x14003e560`
- `0x14003e6b4`
- `0x14003f07c`
- `0x14004bce0`
- `0x14004cfa0`
- `0x1400508a0`

## callees

- `0x1400017a0`
- `0x140008b70`
- `0x140009650`
- `0x140009ca0`
- `0x14000a000`
- `0x14000a230`
- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000edac`
- `0x140016640`
- `0x14004dd50`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14004e1ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004e1ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004df33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e157`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e245`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004df33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e157`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e245`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004df27`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e14b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e239`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004df27`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e14b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e239`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ddf5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004df77`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004ddf5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004df77`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004ddde`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004df60`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004ddde`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004df60`
- `ntoskrnl!KeInitializeEvent` at `0x14004e28a`
- `ntoskrnl!KeInitializeEvent` at `0x14004e28a`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x14004e01f`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x14004e01f`

## pseudocode

```c
__int64 __fastcall SmbCeInitiateExchange(unsigned __int8 *a1)
{
  __int64 v1; // rax
  __int64 v3; // r14
  __int64 v4; // r13
  __int64 v5; // rbp
  unsigned int v6; // ebx
  void *v7; // r15
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  char v11; // cl
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  char v19; // bp
  _QWORD *v21; // rdx
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 11);
  v3 = *((_QWORD *)a1 + 10);
  if ( v1 )
  {
    v4 = *(_QWORD *)(v1 + 96);
    v5 = *(_QWORD *)(v1 + 104);
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  if ( *(_DWORD *)(v3 + 4) == 2 && (*(_WORD *)a1 == 0xED04 || v5 && v4) )
  {
    v6 = 0;
    v7 = (void *)*((_QWORD *)a1 + 15);
    if ( v7 )
      KeInitializeEvent(*((PRKEVENT *)a1 + 15), SynchronizationEvent, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, a1, *a1);
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
      if ( !*((_WORD *)a1 + 30) )
        break;
      switch ( *((_WORD *)a1 + 30) )
      {
        case 1:
          goto LABEL_15;
        case 2:
          goto LABEL_21;
        case 3:
          goto LABEL_27;
      }
LABEL_41:
      ExReleaseResourceLite(&s_SmbCeDbResource);
      KeLeaveCriticalRegion();
      if ( v7 )
      {
        if ( *((_WORD *)a1 + 30) != 4 && v6 == 259 )
        {
          KeWaitForSingleObject(v7, Executive, 0, 0, 0);
          v6 = *((_DWORD *)a1 + 12);
          if ( !v6 )
            continue;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, a1, v6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_qqq(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
            v3,
            v4,
            v5);
        }
      }
      if ( v6 )
      {
        if ( v6 != 259
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, a1, v6);
        }
        return v6;
      }
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
      if ( *(_DWORD *)(v3 + 12) && *(_WORD *)a1 != 0xED04 )
      {
LABEL_100:
        v6 = -1073741300;
        goto LABEL_80;
      }
      v6 = *((_DWORD *)a1 + 10);
      if ( v6 )
        goto LABEL_80;
      v13 = *((_QWORD *)a1 + 10) + 344LL;
      v24 = 0;
      if ( (unsigned int)SmbCepReferenceServerTransport(v13, &v24) )
        goto LABEL_100;
      v14 = v24;
      *((_QWORD *)a1 + 12) = v24;
      if ( v14 )
      {
        *(_QWORD *)(v14 + 504) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids);
        }
        _InterlockedIncrement((volatile signed __int32 *)Initializes + *a1);
        _InterlockedExchange((volatile __int32 *)a1 + 61, 1);
        v15 = *((_QWORD *)a1 + 3);
        if ( v15
          && (*(_QWORD *)(v15 + 216) = a1,
              (v6 = RxSetMinirdrCancelRoutine(*((PRX_CONTEXT *)a1 + 3), (PMRX_CALLDOWN)SmbCeCancelExchange)) != 0) )
        {
          v19 = 0;
        }
        else
        {
          v16 = a1 + 128;
          v17 = *((_QWORD *)a1 + 16);
          if ( (unsigned __int8 *)v17 == a1 + 128 )
            goto LABEL_67;
          if ( *(_QWORD **)(v17 + 8) != v16 )
            goto LABEL_55;
          v21 = (_QWORD *)*((_QWORD *)a1 + 17);
          if ( (_QWORD *)*v21 != v16 )
            goto LABEL_55;
          *v21 = v17;
          *(_QWORD *)(v17 + 8) = v21;
LABEL_67:
          v18 = *(_QWORD **)(v3 + 240);
          if ( *v18 != v3 + 232 )
LABEL_55:
            __fastfail(3u);
          *v16 = v3 + 232;
          *((_QWORD *)a1 + 17) = v18;
          *v18 = v16;
          *(_QWORD *)(v3 + 240) = v16;
          ExReleaseResourceLite(&s_SmbCeDbResource);
          KeLeaveCriticalRegion();
          *((_DWORD *)a1 + 10) = 0;
          v19 = 1;
          *((_DWORD *)a1 + 13) = *(_DWORD *)(v3 + 400);
          v6 = (**((__int64 (__fastcall ***)(unsigned __int8 *))a1 + 19))(a1);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v6);
        }
        if ( v19 )
          return v6;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids);
        }
        v6 = -1073741300;
        SmbCepDereferenceServerTransport(&v24);
      }
LABEL_80:
      ExReleaseResourceLite(&s_SmbCeDbResource);
      KeLeaveCriticalRegion();
      return v6;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, a1, 0);
    v8 = SmbCeReferenceServer((__int64)a1);
    v6 = v8;
    if ( v8 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      {
        goto LABEL_41;
      }
      v23 = 19;
    }
    else
    {
LABEL_15:
      v6 = SmbCeSyncExchangeForSecuritySignature(a1);
      if ( v6 )
        goto LABEL_41;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
          a1,
          *((unsigned __int16 *)a1 + 30));
      }
      v8 = SmbCeReferenceSession(a1);
      v6 = v8;
      if ( v8 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
        {
          goto LABEL_41;
        }
        v23 = 21;
      }
      else
      {
        if ( v8 == 259 && (*((_DWORD *)a1 + 18) & 0x100) == 0 )
          goto LABEL_41;
LABEL_21:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
            a1,
            *((unsigned __int16 *)a1 + 30));
        }
        if ( *a1 == 3 )
          goto LABEL_27;
        v8 = SmbCeReferenceNetRoot(a1);
        v6 = v8;
        if ( v8 >= 0 )
        {
          if ( v8 == 259 && (*((_DWORD *)a1 + 18) & 0x200) == 0 )
            goto LABEL_41;
LABEL_27:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
              a1,
              *((unsigned __int16 *)a1 + 30));
          }
          v9 = *((_QWORD *)a1 + 11);
          if ( v9 )
          {
            v5 = *(_QWORD *)(v9 + 104);
            if ( !v5 )
              goto LABEL_38;
            if ( *(_BYTE *)(v5 + 105) != 1 )
              goto LABEL_38;
            v10 = *((_QWORD *)a1 + 3);
            if ( v10 )
            {
              v11 = *(_BYTE *)(v10 + 32);
              if ( (unsigned __int8)(v11 - 3) > 1u && v11 != 13 )
                goto LABEL_38;
            }
          }
          else
          {
            v5 = 0;
LABEL_38:
            v12 = *((_DWORD *)a1 + 18);
            if ( (v12 & 0x20) == 0 )
              *((_DWORD *)a1 + 18) = v12 | 0x1000;
          }
          *((_WORD *)a1 + 30) = 4;
          v6 = 0;
          goto LABEL_41;
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
        {
          goto LABEL_41;
        }
        v23 = 23;
      }
    }
    WPP_SF_d(v22->AttachedDevice, v23, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, (unsigned int)v8);
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, a1, -1073741248);
  return 3221226048LL;
}

```

## disassembly

```asm
0x14004dd50  push    rbp
0x14004dd52  push    rdi
0x14004dd53  push    r13
0x14004dd55  push    r14
0x14004dd57  sub     rsp, 38h
0x14004dd5b  mov     rax, [rcx+58h]
0x14004dd5f  mov     rdi, rcx
0x14004dd62  mov     r14, [rcx+50h]
0x14004dd66  test    rax, rax
0x14004dd69  jz      loc_14004E25E
0x14004dd6f  mov     r13, [rax+60h]
0x14004dd73  mov     rbp, [rax+68h]
0x14004dd77  cmp     dword ptr [r14+4], 2
0x14004dd7c  mov     [rsp+58h+arg_10], rsi
0x14004dd81  jnz     loc_14004E495
0x14004dd87  mov     eax, 0ED04h
0x14004dd8c  cmp     [rcx], ax
0x14004dd8f  jz      short loc_14004DDA3
0x14004dd91  test    rbp, rbp
0x14004dd94  jz      loc_14004E495
0x14004dd9a  test    r13, r13
0x14004dd9d  jz      loc_14004E495
0x14004dda3  mov     [rsp+58h+arg_8], rbx
0x14004dda8  xor     ebx, ebx
0x14004ddaa  mov     [rsp+58h+arg_18], r12
0x14004ddaf  mov     r12d, 1
0x14004ddb5  mov     [rsp+58h+var_28], r15
0x14004ddba  mov     r15, [rcx+78h]
0x14004ddbe  test    r15, r15
0x14004ddc1  jnz     loc_14004E281
0x14004ddc7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004ddce  lea     rsi, WPP_GLOBAL_Control
0x14004ddd5  cmp     rcx, rsi
0x14004ddd8  jnz     loc_14004E059
0x14004ddde  call    cs:__imp_KeEnterCriticalRegion
0x14004dde5  nop     dword ptr [rax+rax+00h]
0x14004ddea  movzx   edx, r12b; Wait
0x14004ddee  lea     rcx, s_SmbCeDbResource; Resource
0x14004ddf5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004ddfc  nop     dword ptr [rax+rax+00h]
0x14004de01  movzx   ecx, word ptr [rdi+3Ch]
0x14004de05  test    ecx, ecx
0x14004de07  jnz     loc_14004E20A
0x14004de0d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004de14  cmp     rcx, rsi
0x14004de17  jz      short loc_14004DE26
0x14004de19  test    dword ptr [rcx+2Ch], 400h
0x14004de20  jnz     loc_14004E29B
0x14004de26  mov     rcx, rdi
0x14004de29  call    SmbCeReferenceServer
0x14004de2e  mov     ebx, eax
0x14004de30  test    eax, eax
0x14004de32  jnz     loc_14004E2C0
0x14004de38  mov     rcx, rdi
0x14004de3b  call    SmbCeSyncExchangeForSecuritySignature
0x14004de40  mov     ebx, eax
0x14004de42  test    eax, eax
0x14004de44  jnz     loc_14004DF20
0x14004de4a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004de51  cmp     rcx, rsi
0x14004de54  jz      short loc_14004DE63
0x14004de56  test    dword ptr [rcx+2Ch], 400h
0x14004de5d  jnz     loc_14004E301
0x14004de63  mov     rcx, rdi
0x14004de66  call    SmbCeReferenceSession
0x14004de6b  mov     ebx, eax
0x14004de6d  test    eax, eax
0x14004de6f  js      loc_14004E326
0x14004de75  cmp     eax, 103h
0x14004de7a  jz      loc_14004E34A
0x14004de80  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004de87  cmp     rcx, rsi
0x14004de8a  jz      short loc_14004DE99
0x14004de8c  test    dword ptr [rcx+2Ch], 400h
0x14004de93  jnz     loc_14004E35C
0x14004de99  cmp     byte ptr [rdi], 3
0x14004de9c  jz      short loc_14004DEBB
0x14004de9e  mov     rcx, rdi
0x14004dea1  call    SmbCeReferenceNetRoot
0x14004dea6  mov     ebx, eax
0x14004dea8  test    eax, eax
0x14004deaa  js      loc_14004E381
0x14004deb0  cmp     eax, 103h
0x14004deb5  jz      loc_14004E3A3
0x14004debb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004dec2  cmp     rcx, rsi
0x14004dec5  jz      short loc_14004DED4
0x14004dec7  test    dword ptr [rcx+2Ch], 400h
0x14004dece  jnz     loc_14004E3B5
0x14004ded4  mov     rax, [rdi+58h]
0x14004ded8  test    rax, rax
0x14004dedb  jz      short loc_14004DF08
0x14004dedd  mov     rbp, [rax+68h]
0x14004dee1  test    rbp, rbp
0x14004dee4  jz      short loc_14004DF0A
0x14004dee6  cmp     [rbp+69h], r12b
0x14004deea  jnz     short loc_14004DF0A
0x14004deec  mov     rax, [rdi+18h]
0x14004def0  test    rax, rax
0x14004def3  jz      short loc_14004DF18
0x14004def5  movzx   ecx, byte ptr [rax+20h]
0x14004def9  lea     eax, [rcx-3]
0x14004defc  cmp     al, r12b
0x14004deff  jbe     short loc_14004DF18
0x14004df01  cmp     cl, 0Dh
0x14004df04  jz      short loc_14004DF18
0x14004df06  jmp     short loc_14004DF0A
0x14004df08  xor     ebp, ebp
0x14004df0a  mov     eax, [rdi+48h]
0x14004df0d  test    al, 20h
0x14004df0f  jnz     short loc_14004DF18
0x14004df11  bts     eax, 0Ch
0x14004df15  mov     [rdi+48h], eax
0x14004df18  mov     word ptr [rdi+3Ch], 4
0x14004df1e  xor     ebx, ebx
0x14004df20  lea     rcx, s_SmbCeDbResource; Resource
0x14004df27  call    cs:__imp_ExReleaseResourceLite
0x14004df2e  nop     dword ptr [rax+rax+00h]
0x14004df33  call    cs:__imp_KeLeaveCriticalRegion
0x14004df3a  nop     dword ptr [rax+rax+00h]
0x14004df3f  test    r15, r15
0x14004df42  jnz     loc_14004E1C3
0x14004df48  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004df4f  cmp     rcx, rsi
0x14004df52  jnz     loc_14004E08A
0x14004df58  test    ebx, ebx
0x14004df5a  jnz     loc_14004E0DB
0x14004df60  call    cs:__imp_KeEnterCriticalRegion
0x14004df67  nop     dword ptr [rax+rax+00h]
0x14004df6c  movzx   edx, r12b; Wait
0x14004df70  lea     rcx, s_SmbCeDbResource; Resource
0x14004df77  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004df7e  nop     dword ptr [rax+rax+00h]
0x14004df83  cmp     [r14+0Ch], ebx
0x14004df87  jnz     loc_14004E3FB
0x14004df8d  mov     ebx, [rdi+28h]
0x14004df90  xor     r15d, r15d
0x14004df93  test    ebx, ebx
0x14004df95  jnz     loc_14004E232
0x14004df9b  mov     rcx, [rdi+50h]
0x14004df9f  lea     rdx, [rsp+58h+arg_0]
0x14004dfa4  add     rcx, 158h
0x14004dfab  mov     [rsp+58h+arg_0], r15
0x14004dfb0  call    SmbCepReferenceServerTransport
0x14004dfb5  test    eax, eax
0x14004dfb7  jnz     loc_14004E409
0x14004dfbd  mov     rax, [rsp+58h+arg_0]
0x14004dfc2  mov     [rdi+60h], rax
0x14004dfc6  test    rax, rax
0x14004dfc9  jz      loc_14004E413
0x14004dfcf  mov     [rax+1F8h], r15
0x14004dfd6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004dfdd  cmp     rcx, rsi
0x14004dfe0  jz      short loc_14004DFEF
0x14004dfe2  test    dword ptr [rcx+2Ch], 400h
0x14004dfe9  jnz     loc_14004E451
0x14004dfef  movzx   eax, byte ptr [rdi]
0x14004dff2  lea     rcx, Initializes
0x14004dff9  lock inc dword ptr [rcx+rax*4]
0x14004dffd  xchg    r12d, [rdi+0F4h]
0x14004e004  mov     rax, [rdi+18h]
0x14004e008  test    rax, rax
0x14004e00b  jz      short loc_14004E035
0x14004e00d  mov     [rax+0D8h], rdi
0x14004e014  lea     rdx, SmbCeCancelExchange; MRxCancelRoutine
0x14004e01b  mov     rcx, [rdi+18h]; RxContext
0x14004e01f  call    cs:__imp_RxSetMinirdrCancelRoutine
0x14004e026  nop     dword ptr [rax+rax+00h]
0x14004e02b  mov     ebx, eax
0x14004e02d  test    eax, eax
0x14004e02f  jnz     loc_14004E256
0x14004e035  lea     rax, [rdi+80h]
0x14004e03c  mov     rcx, [rax]
0x14004e03f  cmp     rcx, rax
0x14004e042  jz      loc_14004E122
0x14004e048  cmp     [rcx+8], rax
0x14004e04c  jz      loc_14004E268
0x14004e052  mov     ecx, 3
0x14004e057  int     29h; Win8: RtlFailFast(ecx)
0x14004e059  test    dword ptr [rcx+2Ch], 400h
0x14004e060  jz      loc_14004DDDE
0x14004e066  movzx   eax, byte ptr [rdi]
0x14004e069  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004e070  mov     rcx, [rcx+18h]
0x14004e074  mov     edx, 11h
0x14004e079  mov     r9, rdi
0x14004e07c  mov     dword ptr [rsp+58h+Timeout], eax
0x14004e080  call    WPP_SF_qD
0x14004e085  jmp     loc_14004DDDE
0x14004e08a  test    dword ptr [rcx+2Ch], 400h
0x14004e091  jnz     loc_14004E3DA
0x14004e097  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004e09e  cmp     rcx, rsi
0x14004e0a1  jz      loc_14004DF58
0x14004e0a7  test    dword ptr [rcx+2Ch], 400h
0x14004e0ae  jz      loc_14004DF58
0x14004e0b4  mov     rcx, [rcx+18h]
0x14004e0b8  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004e0bf  mov     edx, 1Ah
0x14004e0c4  mov     [rsp+58h+var_30], rbp
0x14004e0c9  mov     r9, r14
0x14004e0cc  mov     [rsp+58h+Timeout], r13
0x14004e0d1  call    WPP_SF_qqq
0x14004e0d6  jmp     loc_14004DF58
0x14004e0db  cmp     ebx, 103h
0x14004e0e1  jz      loc_14004E1A1
0x14004e0e7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004e0ee  cmp     rcx, rsi
0x14004e0f1  jz      loc_14004E1A1
0x14004e0f7  test    dword ptr [rcx+2Ch], 400h
0x14004e0fe  jz      loc_14004E1A1
0x14004e104  mov     rcx, [rcx+18h]
0x14004e108  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004e10f  mov     edx, 1Ch
0x14004e114  mov     dword ptr [rsp+58h+Timeout], ebx
0x14004e118  mov     r9, rdi
0x14004e11b  call    WPP_SF_qD
0x14004e120  jmp     short loc_14004E1A1
0x14004e122  lea     rcx, [r14+0E8h]
0x14004e129  mov     rdx, [rcx+8]
0x14004e12d  cmp     [rdx], rcx
0x14004e130  jnz     loc_14004E052
0x14004e136  mov     [rax], rcx
0x14004e139  mov     [rax+8], rdx
0x14004e13d  mov     [rdx], rax
0x14004e140  mov     [rcx+8], rax
0x14004e144  lea     rcx, s_SmbCeDbResource; Resource
0x14004e14b  call    cs:__imp_ExReleaseResourceLite
0x14004e152  nop     dword ptr [rax+rax+00h]
0x14004e157  call    cs:__imp_KeLeaveCriticalRegion
0x14004e15e  nop     dword ptr [rax+rax+00h]
0x14004e163  mov     [rdi+28h], r15d
0x14004e167  mov     rcx, rdi
0x14004e16a  mov     eax, [r14+190h]
0x14004e171  mov     bpl, 1
0x14004e174  mov     [rdi+34h], eax
0x14004e177  mov     rax, [rdi+98h]
0x14004e17e  mov     rax, [rax]
0x14004e181  call    _guard_dispatch_icall
0x14004e186  mov     ebx, eax
0x14004e188  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004e18f  cmp     rcx, rsi
0x14004e192  jnz     loc_14004E46B
0x14004e198  test    bpl, bpl
0x14004e19b  jz      loc_14004E232
0x14004e1a1  mov     r12, [rsp+58h+arg_18]
0x14004e1a6  mov     eax, ebx
0x14004e1a8  mov     rbx, [rsp+58h+arg_8]
0x14004e1ad  mov     r15, [rsp+58h+var_28]
0x14004e1b2  mov     rsi, [rsp+58h+arg_10]
0x14004e1b7  add     rsp, 38h
0x14004e1bb  pop     r14
0x14004e1bd  pop     r13
0x14004e1bf  pop     rdi
0x14004e1c0  pop     rbp
0x14004e1c1  retn
0x14004e1c3  cmp     word ptr [rdi+3Ch], 4
0x14004e1c8  jz      loc_14004DF48
0x14004e1ce  cmp     ebx, 103h
0x14004e1d4  jnz     loc_14004DF48
0x14004e1da  xor     r9d, r9d; Alertable
0x14004e1dd  mov     [rsp+58h+Timeout], 0; Timeout
0x14004e1e6  xor     r8d, r8d; WaitMode
0x14004e1e9  xor     edx, edx; WaitReason
0x14004e1eb  mov     rcx, r15; Object
0x14004e1ee  call    cs:__imp_KeWaitForSingleObject
0x14004e1f5  nop     dword ptr [rax+rax+00h]
0x14004e1fa  mov     ebx, [rdi+30h]
0x14004e1fd  test    ebx, ebx
0x14004e1ff  jnz     loc_14004DF48
0x14004e205  jmp     loc_14004DDDE
0x14004e20a  sub     ecx, r12d
0x14004e20d  jz      loc_14004DE38
0x14004e213  sub     ecx, r12d
0x14004e216  jz      loc_14004DE80
0x14004e21c  cmp     ecx, r12d
0x14004e21f  jnz     loc_14004DF20
0x14004e225  jmp     loc_14004DEBB
0x14004e22a  test    ebx, ebx
0x14004e22c  jz      loc_14004E004
0x14004e232  lea     rcx, s_SmbCeDbResource; Resource
0x14004e239  call    cs:__imp_ExReleaseResourceLite
0x14004e240  nop     dword ptr [rax+rax+00h]
0x14004e245  call    cs:__imp_KeLeaveCriticalRegion
0x14004e24c  nop     dword ptr [rax+rax+00h]
0x14004e251  jmp     loc_14004E1A1
0x14004e256  xor     bpl, bpl
0x14004e259  jmp     loc_14004E188
0x14004e25e  xor     r13d, r13d
0x14004e261  xor     ebp, ebp
0x14004e263  jmp     loc_14004DD77
0x14004e268  mov     rdx, [rax+8]
0x14004e26c  cmp     [rdx], rax
0x14004e26f  jnz     loc_14004E052
0x14004e275  mov     [rdx], rcx
0x14004e278  mov     [rcx+8], rdx
0x14004e27c  jmp     loc_14004E122
0x14004e281  xor     r8d, r8d; State
0x14004e284  mov     edx, r12d; Type
0x14004e287  mov     rcx, r15; Event
  ... truncated ...
```
