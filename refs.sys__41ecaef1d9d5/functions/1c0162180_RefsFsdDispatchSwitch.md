# RefsFsdDispatchSwitch

- ea: `0x1c0162180`
- end: `0x1c016240c`
- name: `RefsFsdDispatchSwitch`
- size: `652`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1c01620a0`
- `0x1c0162120`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c0161d70`
- `0x1c0162180`
- `0x1c0162414`
- `0x1c016aed4`
- `0x1c0174858`
- `0x1c01c5714`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0162239`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0162239`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c016224d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c016224d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0162266`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0162266`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0184ac5`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0184ac5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01623d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01623d9`

## pseudocode

```c
__int64 __fastcall RefsFsdDispatchSwitch(__int64 a1, __int64 a2, char a3)
{
  __int64 v6; // rdx
  __int64 v7; // r14
  __int64 v8; // rax
  NTSTATUS v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned int Information; // eax
  unsigned int v13; // ebx
  __int64 v15; // [rsp+28h] [rbp-80h] BYREF
  BOOL v16; // [rsp+30h] [rbp-78h]
  _QWORD v17[2]; // [rsp+38h] [rbp-70h] BYREF
  _OWORD v18[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v19; // [rsp+68h] [rbp-40h]
  __int128 v20; // [rsp+70h] [rbp-38h] BYREF

  v17[1] = a2;
  memset(v18, 0, sizeof(v18));
  v19 = 0;
  v20 = 0;
  v17[0] = 0;
  v7 = RefsInitializeTopLevelIrp(v18, 0, 0);
  v8 = 0;
  if ( a1 )
    v8 = a1;
  v15 = v8;
  LOBYTE(v6) = a3;
  v9 = RefsInitializeIrpContext(a2, v6, 0, &v15);
  if ( v9 >= 0 )
  {
    v10 = v15;
    *(_WORD *)(v15 + 2) = 336;
    v11 = *(_QWORD *)(v7 + 32);
    if ( !v11 )
    {
      *(_DWORD *)(v7 + 4) = 1397140410;
      *(_QWORD *)(v7 + 32) = v10;
      *(_DWORD *)(v10 + 8) |= 0x100000u;
      IoSetTopLevelIrp((PIRP)v7);
      v11 = *(_QWORD *)(v7 + 32);
    }
    *(_QWORD *)(v10 + 104) = v11;
    KeEnterCriticalRegion();
    v16 = (int)IoPropagateActivityIdToThread(a2, &v20, v17) >= 0;
    if ( v10 )
      RefsPreRequestProcessingExtend(v10);
    switch ( *(_BYTE *)(v10 + 40) )
    {
      case 5:
        Information = RefsCommonQueryInformation(v10, a2);
        break;
      case 0xA:
        Information = RefsCommonQueryVolumeInfo(v10, a2);
        break;
      case 0xB:
        Information = RefsCommonSetVolumeInfo(v10, a2);
        break;
      case 0x14:
        Information = RefsCommonQuerySecurityInfo(v10, a2);
        break;
      case 0x15:
        Information = RefsCommonSetSecurityInfo(v10, a2);
        break;
      default:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids,
            3221225488LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741808);
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741808);
        RefsExtendedCompleteRequestInternal(v15, a2, 3221225488LL);
        v13 = -1073741808;
        goto LABEL_28;
    }
    v13 = Information;
LABEL_28:
    if ( v16 )
      IoClearActivityIdThread(v17[0]);
    KeLeaveCriticalRegion();
    return v13;
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(v9);
  RefsExtendedCompleteRequestInternal(0, a2, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c0162180  mov     r11, rsp
0x1c0162183  mov     [r11+20h], rbx
0x1c0162187  push    rsi
0x1c0162188  push    rdi
0x1c0162189  push    r14
0x1c016218b  sub     rsp, 90h
0x1c0162192  mov     rax, cs:__security_cookie
0x1c0162199  xor     rax, rsp
0x1c016219c  mov     [rsp+0A8h+var_28], rax
0x1c01621a4  mov     dil, r8b
0x1c01621a7  mov     rsi, rdx
0x1c01621aa  mov     rbx, rcx
0x1c01621ad  mov     [rsp+0A8h+var_68], rdx
0x1c01621b2  xorps   xmm0, xmm0
0x1c01621b5  xor     eax, eax
0x1c01621b7  movups  [rsp+0A8h+var_60], xmm0
0x1c01621bc  movups  [rsp+0A8h+var_50], xmm0
0x1c01621c1  mov     [r11-40h], rax
0x1c01621c5  movups  [rsp+0A8h+var_38], xmm0
0x1c01621ca  and     [r11-70h], rax
0x1c01621ce  xor     r8d, r8d
0x1c01621d1  xor     edx, edx
0x1c01621d3  lea     rcx, [r11-60h]
0x1c01621d7  call    RefsInitializeTopLevelIrp
0x1c01621dc  mov     r14, rax
0x1c01621df  xor     eax, eax
0x1c01621e1  test    rbx, rbx
0x1c01621e4  cmovnz  rax, rbx
0x1c01621e8  mov     [rsp+0A8h+var_80], rax
0x1c01621ed  lea     r9, [rsp+0A8h+var_80]
0x1c01621f2  xor     r8d, r8d
0x1c01621f5  mov     dl, dil
0x1c01621f8  mov     rcx, rsi
0x1c01621fb  call    RefsInitializeIrpContext
0x1c0162200  mov     ebx, eax
0x1c0162202  mov     [rsp+0A8h+Status], eax
0x1c0162206  test    eax, eax
0x1c0162208  js      loc_1C0184A62
0x1c016220e  mov     eax, 150h
0x1c0162213  mov     rdi, [rsp+0A8h+var_80]
0x1c0162218  mov     [rdi+2], ax
0x1c016221c  mov     rax, [r14+20h]
0x1c0162220  test    rax, rax
0x1c0162223  jnz     short loc_1C0162249
0x1c0162225  mov     dword ptr [r14+4], 5346ABBAh
0x1c016222d  mov     [r14+20h], rdi
0x1c0162231  bts     dword ptr [rdi+8], 14h
0x1c0162236  mov     rcx, r14; Irp
0x1c0162239  call    cs:__imp_IoSetTopLevelIrp
0x1c0162240  nop     dword ptr [rax+rax+00h]
0x1c0162245  mov     rax, [r14+20h]
0x1c0162249  mov     [rdi+68h], rax
0x1c016224d  call    cs:__imp_KeEnterCriticalRegion
0x1c0162254  nop     dword ptr [rax+rax+00h]
0x1c0162259  lea     r8, [rsp+0A8h+var_70]
0x1c016225e  lea     rdx, [rsp+0A8h+var_38]
0x1c0162263  mov     rcx, rsi
0x1c0162266  call    cs:__imp_IoPropagateActivityIdToThread
0x1c016226d  nop     dword ptr [rax+rax+00h]
0x1c0162272  xor     ecx, ecx
0x1c0162274  lea     edx, [rcx+1]
0x1c0162277  test    eax, eax
0x1c0162279  cmovns  ecx, edx
0x1c016227c  mov     [rsp+0A8h+var_78], ecx
0x1c0162280  cmp     ebx, 0C0000188h
0x1c0162286  jz      short loc_1C01622EA
0x1c0162288  test    rdi, rdi
0x1c016228b  jz      short loc_1C0162295
0x1c016228d  mov     rcx, rdi
0x1c0162290  call    RefsPreRequestProcessingExtend
0x1c0162295  movzx   ecx, byte ptr [rdi+28h]
0x1c0162299  sub     ecx, 5
0x1c016229c  jnz     short loc_1C01622B4
0x1c016229e  mov     rdx, rsi
0x1c01622a1  mov     rcx, rdi
0x1c01622a4  call    RefsCommonQueryInformation
0x1c01622a9  mov     ebx, eax
0x1c01622ab  mov     [rsp+0A8h+Status], eax
0x1c01622af  jmp     loc_1C01623A9
0x1c01622b4  sub     ecx, 5
0x1c01622b7  jz      short loc_1C01622D0
0x1c01622b9  sub     ecx, 1
0x1c01622bc  jz      short loc_1C01622DD
0x1c01622be  sub     ecx, 9
0x1c01622c1  jnz     short loc_1C01622F4
0x1c01622c3  mov     rdx, rsi
0x1c01622c6  mov     rcx, rdi
0x1c01622c9  call    RefsCommonQuerySecurityInfo
0x1c01622ce  jmp     short loc_1C01622A9
0x1c01622d0  mov     rdx, rsi
0x1c01622d3  mov     rcx, rdi
0x1c01622d6  call    RefsCommonQueryVolumeInfo
0x1c01622db  jmp     short loc_1C01622A9
0x1c01622dd  mov     rdx, rsi
0x1c01622e0  mov     rcx, rdi
0x1c01622e3  call    RefsCommonSetVolumeInfo
0x1c01622e8  jmp     short loc_1C01622A9
0x1c01622ea  mov     rcx, rdi
0x1c01622ed  call    RefsCheckpointForLogFileFull
0x1c01622f2  jmp     short loc_1C0162288
0x1c01622f4  cmp     ecx, 1
0x1c01622f7  jz      loc_1C0162399
0x1c01622fd  lea     rax, WPP_GLOBAL_Control
0x1c0162304  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016230b  cmp     rcx, rax
0x1c016230e  jz      short loc_1C016233E
0x1c0162310  test    dword ptr [rcx+2Ch], 100h
0x1c0162317  jz      short loc_1C016233E
0x1c0162319  cmp     byte ptr [rcx+29h], 4
0x1c016231d  jb      short loc_1C016233E
0x1c016231f  mov     edx, 1Fh
0x1c0162324  mov     ebx, 0C0000010h
0x1c0162329  mov     r9d, ebx
0x1c016232c  lea     r8, WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids
0x1c0162333  mov     rcx, [rcx+18h]
0x1c0162337  call    WPP_SF_D
0x1c016233c  jmp     short loc_1C0162343
0x1c016233e  mov     ebx, 0C0000010h
0x1c0162343  mov     al, cs:RefsStatusDebugEnabled
0x1c0162349  test    al, al
0x1c016234b  jz      short loc_1C0162361
0x1c016234d  mov     r8d, 11E6h
0x1c0162353  lea     rdx, aNtfsdataC; "NtfsData.c"
0x1c016235a  mov     ecx, ebx; Status
0x1c016235c  call    RefsStatusDebug
0x1c0162361  mov     [rsp+0A8h+Status], ebx
0x1c0162365  mov     al, cs:RefsStatusDebugEnabled
0x1c016236b  test    al, al
0x1c016236d  jz      short loc_1C0162383
0x1c016236f  mov     r8d, 11E7h
0x1c0162375  lea     rdx, aNtfsdataC; "NtfsData.c"
0x1c016237c  mov     ecx, ebx; Status
0x1c016237e  call    RefsStatusDebug
0x1c0162383  mov     r8d, ebx
0x1c0162386  mov     rdx, rsi
0x1c0162389  mov     rcx, [rsp+0A8h+var_80]
0x1c016238e  call    RefsExtendedCompleteRequestInternal
0x1c0162393  mov     ebx, [rsp+0A8h+Status]
0x1c0162397  jmp     short loc_1C01623A9
0x1c0162399  mov     rdx, rsi
0x1c016239c  mov     rcx, rdi
0x1c016239f  call    RefsCommonSetSecurityInfo
0x1c01623a4  jmp     loc_1C01622A9
0x1c01623a9  jmp     short loc_1C01623CE
0x1c01623ab  mov     r8d, eax
0x1c01623ae  mov     rsi, [rsp+0A8h+var_68]
0x1c01623b3  mov     rdx, rsi
0x1c01623b6  mov     rdi, [rsp+0A8h+var_80]
0x1c01623bb  mov     rcx, rdi
0x1c01623be  call    RefsProcessException
0x1c01623c3  mov     ebx, eax
0x1c01623c5  mov     [rsp+0A8h+Status], eax
0x1c01623c9  jmp     loc_1C0184A9A
0x1c01623ce  cmp     [rsp+0A8h+var_78], 0
0x1c01623d3  jnz     loc_1C0184AC0
0x1c01623d9  call    cs:__imp_KeLeaveCriticalRegion
0x1c01623e0  nop     dword ptr [rax+rax+00h]
0x1c01623e5  mov     eax, ebx
0x1c01623e7  mov     rcx, [rsp+0A8h+var_28]
0x1c01623ef  xor     rcx, rsp; StackCookie
0x1c01623f2  call    __security_check_cookie
0x1c01623f7  mov     rbx, [rsp+0A8h+arg_18]
0x1c01623ff  add     rsp, 90h
0x1c0162406  pop     r14
0x1c0162408  pop     rdi
0x1c0162409  pop     rsi
0x1c016240a  retn
0x1c017f2cb  push    rbp
0x1c017f2cd  sub     rsp, 20h
0x1c017f2d1  mov     rbp, rdx
0x1c017f2d4  mov     rdx, rcx
0x1c017f2d7  mov     rcx, [rbp+28h]
0x1c017f2db  call    RefsExceptionFilter
0x1c017f2e0  nop
0x1c017f2e1  add     rsp, 20h
0x1c017f2e5  pop     rbp
0x1c017f2e6  retn
0x1c0184a62  mov     al, cs:RefsStatusDebugEnabled
0x1c0184a68  test    al, al
0x1c0184a6a  jz      short loc_1C0184A82
0x1c0184a6c  mov     r8d, 11A4h
0x1c0184a72  lea     rdx, aNtfsdataC; "NtfsData.c"
0x1c0184a79  mov     ecx, [rsp+0A8h+Status]; Status
0x1c0184a7d  call    RefsStatusDebug
0x1c0184a82  mov     r8d, [rsp+0A8h+Status]
0x1c0184a87  mov     rdx, rsi
0x1c0184a8a  xor     ecx, ecx
0x1c0184a8c  call    RefsExtendedCompleteRequestInternal
0x1c0184a91  mov     eax, [rsp+0A8h+Status]
0x1c0184a95  jmp     loc_1C01623E7
0x1c0184a9a  cmp     eax, 0C00000D8h
0x1c0184a9f  jz      loc_1C0162280
0x1c0184aa5  cmp     eax, 0C00001A8h
0x1c0184aaa  jz      loc_1C0162280
0x1c0184ab0  cmp     eax, 0C0000188h
0x1c0184ab5  jz      loc_1C0162280
0x1c0184abb  jmp     loc_1C01623CE
0x1c0184ac0  mov     rcx, [rsp+0A8h+var_70]
0x1c0184ac5  call    cs:__imp_IoClearActivityIdThread
0x1c0184acc  nop     dword ptr [rax+rax+00h]
0x1c0184ad1  nop
0x1c0184ad2  jmp     loc_1C01623D9
```
