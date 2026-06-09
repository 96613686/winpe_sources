# RefsFsdPnp

- ea: `0x1c0174d50`
- end: `0x1c0174fc6`
- name: `RefsFsdPnp`
- size: `630`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003cac4`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c016d3c4`
- `0x1c0174d50`
- `0x1c0174fcc`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0174e65`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0174e65`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0174dab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0174dab`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0174dc9`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0174dc9`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0188dd5`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0188dd5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0174f87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0174f87`

## pseudocode

```c
__int64 __fastcall RefsFsdPnp(__int64 a1, __int64 a2)
{
  int v2; // edi
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  BOOL v6; // r15d
  unsigned __int8 v7; // al
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rbx
  _BYTE v16[4]; // [rsp+20h] [rbp-98h] BYREF
  NTSTATUS Status; // [rsp+24h] [rbp-94h]
  __int64 v18; // [rsp+28h] [rbp-90h] BYREF
  __int64 v19; // [rsp+30h] [rbp-88h] BYREF
  BOOL v20; // [rsp+38h] [rbp-80h]
  _QWORD v21[3]; // [rsp+40h] [rbp-78h] BYREF
  _OWORD v22[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v23; // [rsp+78h] [rbp-40h]
  __int128 v24; // [rsp+80h] [rbp-38h] BYREF

  v19 = a2;
  v2 = 0;
  Status = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v3 = 0;
  v18 = 0;
  v16[0] = 0;
  v24 = 0;
  v21[0] = 0;
  KeEnterCriticalRegion();
  v6 = (int)IoPropagateActivityIdToThread(v19, &v24, v21) >= 0;
  v20 = v6;
  v7 = *(_BYTE *)(*(_QWORD *)(v19 + 184) + 1LL);
  LOBYTE(v4) = !v7 || v7 != 23 && v7 > 3u;
  LOBYTE(v5) = v4;
  v9 = RefsInitializeTopLevelIrp(v22, v4, v5);
  v21[1] = v9;
  while ( v2 >= 0 && !v3 )
  {
    LOBYTE(v10) = 1;
    LOBYTE(v8) = 1;
    RefsInitializeIrpContext(v19, v8, v10, &v18);
    v12 = *(_QWORD *)(v9 + 32);
    if ( v12 )
    {
      v3 = v18;
    }
    else
    {
      *(_DWORD *)(v9 + 4) = 1397140410;
      v3 = v18;
      *(_QWORD *)(v9 + 32) = v18;
      *(_DWORD *)(v3 + 8) |= 0x100000u;
      IoSetTopLevelIrp((PIRP)v9);
      v12 = *(_QWORD *)(v9 + 32);
    }
    *(_QWORD *)(v3 + 104) = v12;
LABEL_11:
    if ( v3 )
      RefsPreRequestProcessingExtend(v3);
    v2 = RefsCommonPnp(v3, &v19, v16);
    Status = v2;
  }
  if ( v2 == -1073741432 )
  {
    RefsCheckpointForLogFileFull(v3);
    goto LABEL_11;
  }
  if ( v2 == -1073741608 || v2 == -1073741400 )
    goto LABEL_11;
  if ( v16[0] )
  {
    LOBYTE(v10) = 1;
    RefsAcquireExclusiveVcb(v3, *(_QWORD *)(v3 + 64), v10, v11);
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v3 + 64) + 220LL));
    v13 = *(_QWORD *)(v3 + 64);
    v14 = v18;
    RefsReleaseVcbCheckDelete(v18, v13);
    *(_DWORD *)(v14 + 8) &= ~0x10000u;
    v2 = Status;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsExtendedCompleteRequestInternal(v18, 0, (unsigned int)v2);
  }
  if ( v6 )
    IoClearActivityIdThread(v21[0]);
  KeLeaveCriticalRegion();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1c0174d50  mov     r11, rsp
0x1c0174d53  mov     [r11+8], rbx
0x1c0174d57  mov     [r11+18h], rsi
0x1c0174d5b  push    rdi
0x1c0174d5c  push    r14
0x1c0174d5e  push    r15
0x1c0174d60  sub     rsp, 0A0h
0x1c0174d67  mov     rax, cs:__security_cookie
0x1c0174d6e  xor     rax, rsp
0x1c0174d71  mov     [rsp+0B8h+var_28], rax
0x1c0174d79  mov     [rsp+0B8h+var_88], rdx
0x1c0174d7e  xor     edi, edi
0x1c0174d80  mov     [rsp+0B8h+Status], edi
0x1c0174d84  xorps   xmm0, xmm0
0x1c0174d87  xor     eax, eax
0x1c0174d89  movups  [rsp+0B8h+var_60], xmm0
0x1c0174d8e  movups  [rsp+0B8h+var_50], xmm0
0x1c0174d93  mov     [r11-40h], rax
0x1c0174d97  xor     ebx, ebx
0x1c0174d99  mov     [rsp+0B8h+var_90], rbx
0x1c0174d9e  mov     [rsp+0B8h+var_98], al
0x1c0174da2  movups  xmmword ptr [r11-38h], xmm0
0x1c0174da7  and     [r11-78h], rax
0x1c0174dab  call    cs:__imp_KeEnterCriticalRegion
0x1c0174db2  nop     dword ptr [rax+rax+00h]
0x1c0174db7  lea     r8, [rsp+0B8h+var_78]
0x1c0174dbc  lea     rdx, [rsp+0B8h+var_38]
0x1c0174dc4  mov     rcx, [rsp+0B8h+var_88]
0x1c0174dc9  call    cs:__imp_IoPropagateActivityIdToThread
0x1c0174dd0  nop     dword ptr [rax+rax+00h]
0x1c0174dd5  xor     r15d, r15d
0x1c0174dd8  lea     r14d, [rdi+1]
0x1c0174ddc  test    eax, eax
0x1c0174dde  cmovns  r15d, r14d
0x1c0174de2  mov     [rsp+0B8h+var_80], r15d
0x1c0174de7  mov     rax, [rsp+0B8h+var_88]
0x1c0174dec  mov     rcx, [rax+0B8h]
0x1c0174df3  mov     al, [rcx+1]
0x1c0174df6  test    al, al
0x1c0174df8  jz      short loc_1C0174E0A
0x1c0174dfa  cmp     al, 17h
0x1c0174dfc  jz      loc_1C0174FBF
0x1c0174e02  cmp     al, 3
0x1c0174e04  jbe     loc_1C0174FBF
0x1c0174e0a  mov     dl, r14b
0x1c0174e0d  mov     r8b, dl
0x1c0174e10  lea     rcx, [rsp+0B8h+var_60]
0x1c0174e15  call    RefsInitializeTopLevelIrp
0x1c0174e1a  mov     rsi, rax
0x1c0174e1d  mov     [rsp+0B8h+var_70], rax
0x1c0174e22  test    edi, edi
0x1c0174e24  js      short loc_1C0174E8F
0x1c0174e26  test    rbx, rbx
0x1c0174e29  jnz     short loc_1C0174E8F
0x1c0174e2b  lea     r9, [rsp+0B8h+var_90]
0x1c0174e30  mov     r8b, r14b
0x1c0174e33  mov     dl, r14b
0x1c0174e36  mov     rcx, [rsp+0B8h+var_88]
0x1c0174e3b  call    RefsInitializeIrpContext
0x1c0174e40  mov     rax, [rsi+20h]
0x1c0174e44  test    rax, rax
0x1c0174e47  jnz     loc_1C0174F1A
0x1c0174e4d  mov     dword ptr [rsi+4], 5346ABBAh
0x1c0174e54  mov     rbx, [rsp+0B8h+var_90]
0x1c0174e59  mov     [rsi+20h], rbx
0x1c0174e5d  bts     dword ptr [rbx+8], 14h
0x1c0174e62  mov     rcx, rsi; Irp
0x1c0174e65  call    cs:__imp_IoSetTopLevelIrp
0x1c0174e6c  nop     dword ptr [rax+rax+00h]
0x1c0174e71  mov     rax, [rsi+20h]
0x1c0174e75  mov     [rbx+68h], rax
0x1c0174e79  test    rbx, rbx
0x1c0174e7c  jz      loc_1C0174F31
0x1c0174e82  mov     rcx, rbx
0x1c0174e85  call    RefsPreRequestProcessingExtend
0x1c0174e8a  jmp     loc_1C0174F31
0x1c0174e8f  cmp     edi, 0C0000188h
0x1c0174e95  jz      loc_1C0174F24
0x1c0174e9b  cmp     edi, 0C00000D8h
0x1c0174ea1  jz      short loc_1C0174E79
0x1c0174ea3  cmp     edi, 0C00001A8h
0x1c0174ea9  jz      short loc_1C0174E79
0x1c0174eab  cmp     [rsp+0B8h+var_98], 0
0x1c0174eb0  jnz     short loc_1C0174EB7
0x1c0174eb2  jmp     loc_1C0174F7E
0x1c0174eb7  mov     r8b, r14b
0x1c0174eba  mov     rdx, [rbx+40h]
0x1c0174ebe  mov     rcx, rbx
0x1c0174ec1  call    RefsAcquireExclusiveVcb
0x1c0174ec6  mov     rax, [rbx+40h]
0x1c0174eca  lock dec dword ptr [rax+0DCh]
0x1c0174ed1  mov     rdx, [rbx+40h]
0x1c0174ed5  mov     rbx, [rsp+0B8h+var_90]
0x1c0174eda  mov     rcx, rbx
0x1c0174edd  call    RefsReleaseVcbCheckDelete
0x1c0174ee2  btr     dword ptr [rbx+8], 10h
0x1c0174ee7  mov     al, cs:RefsStatusDebugEnabled
0x1c0174eed  mov     edi, [rsp+0B8h+Status]
0x1c0174ef1  test    al, al
0x1c0174ef3  jz      short loc_1C0174F09
0x1c0174ef5  mov     r8d, 0CDh
0x1c0174efb  lea     rdx, aPnpC; "Pnp.c"
0x1c0174f02  mov     ecx, edi; Status
0x1c0174f04  call    RefsStatusDebug
0x1c0174f09  mov     r8d, edi
0x1c0174f0c  xor     edx, edx
0x1c0174f0e  mov     rcx, [rsp+0B8h+var_90]
0x1c0174f13  call    RefsExtendedCompleteRequestInternal
0x1c0174f18  jmp     short loc_1C0174EB2
0x1c0174f1a  mov     rbx, [rsp+0B8h+var_90]
0x1c0174f1f  jmp     loc_1C0174E75
0x1c0174f24  mov     rcx, rbx
0x1c0174f27  call    RefsCheckpointForLogFileFull
0x1c0174f2c  jmp     loc_1C0174E79
0x1c0174f31  lea     r8, [rsp+0B8h+var_98]
0x1c0174f36  lea     rdx, [rsp+0B8h+var_88]
0x1c0174f3b  mov     rcx, rbx
0x1c0174f3e  call    RefsCommonPnp
0x1c0174f43  mov     edi, eax
0x1c0174f45  mov     [rsp+0B8h+Status], eax
0x1c0174f49  jmp     loc_1C0174E22
0x1c0174f4e  mov     r8d, eax
0x1c0174f51  mov     rdx, [rsp+0B8h+var_88]
0x1c0174f56  mov     rbx, [rsp+0B8h+var_90]
0x1c0174f5b  mov     rcx, rbx
0x1c0174f5e  call    RefsProcessException
0x1c0174f63  mov     edi, eax
0x1c0174f65  mov     [rsp+0B8h+Status], eax
0x1c0174f69  mov     r14d, 1
0x1c0174f6f  mov     rsi, [rsp+0B8h+var_70]
0x1c0174f74  mov     r15d, [rsp+0B8h+var_80]
0x1c0174f79  jmp     loc_1C0174E22
0x1c0174f7e  test    r15d, r15d
0x1c0174f81  jnz     loc_1C0188DD0
0x1c0174f87  call    cs:__imp_KeLeaveCriticalRegion
0x1c0174f8e  nop     dword ptr [rax+rax+00h]
0x1c0174f93  mov     eax, edi
0x1c0174f95  mov     rcx, [rsp+0B8h+var_28]
0x1c0174f9d  xor     rcx, rsp; StackCookie
0x1c0174fa0  call    __security_check_cookie
0x1c0174fa5  lea     r11, [rsp+0B8h+var_18]
0x1c0174fad  mov     rbx, [r11+20h]
0x1c0174fb1  mov     rsi, [r11+30h]
0x1c0174fb5  mov     rsp, r11
0x1c0174fb8  pop     r15
0x1c0174fba  pop     r14
0x1c0174fbc  pop     rdi
0x1c0174fbd  retn
0x1c0174fbf  xor     dl, dl
0x1c0174fc1  jmp     loc_1C0174E0D
0x1c0180915  push    rbp
0x1c0180917  sub     rsp, 20h
0x1c018091b  mov     rbp, rdx
0x1c018091e  mov     [rbp+50h], rcx
0x1c0180922  mov     rdx, rcx
0x1c0180925  mov     rcx, [rbp+28h]
0x1c0180929  call    RefsExceptionFilter
0x1c018092e  nop
0x1c018092f  add     rsp, 20h
0x1c0180933  pop     rbp
0x1c0180934  retn
0x1c0188dd0  mov     rcx, [rsp+0B8h+var_78]
0x1c0188dd5  call    cs:__imp_IoClearActivityIdThread
0x1c0188ddc  nop     dword ptr [rax+rax+00h]
0x1c0188de1  nop
0x1c0188de2  jmp     loc_1C0174F87
```
