# ApplyCalibrationCurvesThroughGDI(HMONITOR__ *,ICalibrationCurve *,ICalibrationCurve *,ICalibrationCurve *)

- ea: `0x180026090`
- end: `0x18002652c`
- name: `?ApplyCalibrationCurvesThroughGDI@@YAJPEAUHMONITOR__@@PEAVICalibrationCurve@@11@Z`
- size: `1180`
- prototype: `__int64 __fastcall(HMONITOR hMonitor, struct ICalibrationCurve *, struct ICalibrationCurve *, struct ICalibrationCurve *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180019c48`

## callees

- `0x18001582c`
- `0x180015e7c`
- `0x1800171c8`
- `0x180026090`
- `0x18002e5f0`
- `0x18002e614`
- `0x18002eab4`
- `0x18002f2f4`
- `0x180084010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026503`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026225`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x180026126`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x180026126`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800261ee`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800261ee`

## pseudocode

```c
__int64 __fastcall ApplyCalibrationCurvesThroughGDI(
        HMONITOR hMonitor,
        struct ICalibrationCurve *a2,
        struct ICalibrationCurve *a3,
        struct ICalibrationCurve *a4)
{
  signed int LastError; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rdi
  LONG DeviceInfo; // eax
  bool v12; // sf
  __int64 v13; // rdx
  __int64 v14; // rbx
  unsigned int v15; // r13d
  __int64 v16; // rsi
  __int16 v17; // di
  __int16 v18; // bx
  float v19; // xmm0_4
  __int16 v20; // cx
  __int64 v22; // [rsp+38h] [rbp-D0h]
  __int64 v23; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor_8; // [rsp+58h] [rbp-B0h] BYREF
  int mi_4; // [rsp+68h] [rbp-A0h] BYREF
  __int128 mi_8; // [rsp+6Ch] [rbp-9Ch]
  __int128 mi_24; // [rsp+7Ch] [rbp-8Ch]
  __int128 v29; // [rsp+8Ch] [rbp-7Ch]
  __int128 v30; // [rsp+9Ch] [rbp-6Ch]
  __int128 v31; // [rsp+ACh] [rbp-5Ch]
  __int128 v32; // [rsp+BCh] [rbp-4Ch]
  int v33; // [rsp+CCh] [rbp-3Ch]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v35[144]; // [rsp+ECh] [rbp-1Ch] BYREF
  WCHAR sourceString[134]; // [rsp+17Ch] [rbp+74h] BYREF
  struct DISPLAYCONFIG_PATH_INFO UserData; // [rsp+288h] [rbp+180h] BYREF
  _WORD v38[768]; // [rsp+2D8h] [rbp+1D0h] BYREF

  if ( !hMonitor || !a2 || !a3 || !a4 )
    goto LABEL_20;
  mi_4 = 104;
  mi_8 = 0;
  v33 = 0;
  mi_24 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( !GetMonitorInfoW(hMonitor, (LPMONITORINFO)&mi_4) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_21;
  }
  string = 0;
  memset(&UserData, 0, sizeof(UserData));
  v10 = (unsigned __int16 *)operator new[](0x208u);
  v9 = InternalTranslateHMonitorToICMName(hMonitor, v10);
  if ( v9 >= 0 )
  {
    v9 = InternalTranslateICMNameToPath(v10, &UserData);
    if ( v9 >= 0 )
    {
      memset_0(v35, 0, 0x190u);
      requestPacket.adapterId = UserData.targetInfo.adapterId;
      requestPacket.id = UserData.targetInfo.id;
      requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
      requestPacket.size = 420;
      DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
      v12 = DeviceInfo < 0;
      if ( DeviceInfo > 0 )
        v12 = 1;
      if ( !v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( sourceString[v13] );
        v9 = WindowsCreateString(sourceString, v13, &string);
        goto LABEL_16;
      }
LABEL_20:
      v9 = -2147024809;
      goto LABEL_21;
    }
  }
LABEL_16:
  if ( v9 >= 0 )
  {
    v14 = 0;
    v15 = 0;
    v22 = 0;
    do
    {
      v16 = 3 * v14;
      v17 = (unsigned __int16)(int)(float)((float)(fminf(
                                                     1.0,
                                                     fmaxf(
                                                       0.0,
                                                       COERCE_FLOAT(COERCE_UNSIGNED_INT64((**(double (__fastcall ***)(struct ICalibrationCurve *))a2)(a2)))))
                                                 * 255.0)
                                         + 0.5) << 8;
      v18 = (unsigned __int16)(int)(float)((float)(fminf(
                                                     1.0,
                                                     fmaxf(
                                                       0.0,
                                                       COERCE_FLOAT(COERCE_UNSIGNED_INT64((**(double (__fastcall ***)(struct ICalibrationCurve *))a3)(a3)))))
                                                 * 255.0)
                                         + 0.5) << 8;
      v19 = (**(float (__fastcall ***)(struct ICalibrationCurve *))a4)(a4);
      ++v15;
      v38[v16] = v17 + __ROR2__(v17, 8);
      v38[v16 + 1] = v18 + __ROR2__(v18, 8);
      v14 = ++v22;
      v20 = (unsigned __int16)(int)(float)((float)(fminf(1.0, fmaxf(0.0, v19)) * 255.0) + 0.5) << 8;
      v38[v16 + 2] = v20 + __ROR2__(v20, 8);
    }
    while ( v15 < 0x100 );
    EventDescriptor_8 = (EVENT_DESCRIPTOR)xmmword_18008C718;
    v9 = ModernColorSetGDILut(string, (struct _GUID *)&EventDescriptor_8, (struct UINT16Triple (*)[256])v38);
    WindowsDeleteString(string);
  }
LABEL_21:
  if ( (unsigned int)dword_18009E048 > 5 && (qword_18009E058 & 1) != 0 && (qword_18009E060 & 1) == qword_18009E060 )
  {
    LODWORD(v23) = v9;
    *(_QWORD *)&UserData.targetInfo.modeInfoIdx = &v23;
    UserData.sourceInfo.adapterId = (LUID)off_18009E050;
    *(_QWORD *)&UserData.targetInfo.rotation = 4;
    *(_QWORD *)&EventDescriptor_8.Id = 0x50B000000LL;
    EventDescriptor_8.Keyword = 1;
    UserData.sourceInfo.id = *(unsigned __int16 *)off_18009E050;
    *(_QWORD *)&UserData.sourceInfo.statusFlags = byte_1800920F1;
    UserData.sourceInfo.modeInfoIdx = 2;
    *(_QWORD *)&UserData.targetInfo.adapterId.HighPart = 0x100000031LL;
    EventWriteTransfer(qword_18009E068, &EventDescriptor_8, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)&UserData);
  }
  operator delete(0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026090  mov     r11, rsp
0x180026093  push    rbp
0x180026094  push    rbx
0x180026095  push    rsi
0x180026096  lea     rbp, [r11-878h]
0x18002609d  sub     rsp, 960h
0x1800260a4  mov     rax, cs:__security_cookie
0x1800260ab  xor     rax, rsp
0x1800260ae  mov     [rbp+870h+var_A0], rax
0x1800260b5  mov     [r11-20h], rdi
0x1800260b9  xor     esi, esi
0x1800260bb  mov     [r11-28h], r12
0x1800260bf  mov     r12, r9
0x1800260c2  mov     [r11-38h], r14
0x1800260c6  mov     r14, rdx
0x1800260c9  mov     [r11-40h], r15
0x1800260cd  mov     r15, r8
0x1800260d0  mov     rbx, rcx
0x1800260d3  test    rcx, rcx
0x1800260d6  jz      loc_1800263F2
0x1800260dc  test    rdx, rdx
0x1800260df  jz      loc_1800263F2
0x1800260e5  test    r8, r8
0x1800260e8  jz      loc_1800263F2
0x1800260ee  test    r9, r9
0x1800260f1  jz      loc_1800263F2
0x1800260f7  xorps   xmm0, xmm0
0x1800260fa  mov     [rsp+970h+mi.rcMonitor.left], 68h ; 'h'
0x180026102  xor     eax, eax
0x180026104  lea     rdx, [rsp+970h+mi.rcMonitor]; lpmi
0x180026109  movups  xmmword ptr [rsp+970h+mi.rcMonitor.top], xmm0
0x18002610e  mov     [rbp+870h+var_8AC], eax
0x180026111  movups  xmmword ptr [rsp+970h+mi.rcWork.top], xmm0
0x180026116  movups  [rbp+870h+var_8EC], xmm0
0x18002611a  movups  [rbp+870h+var_8DC], xmm0
0x18002611e  movups  [rbp+870h+var_8CC], xmm0
0x180026122  movups  [rbp+870h+var_8BC], xmm0
0x180026126  call    cs:__imp_GetMonitorInfoW
0x18002612c  test    eax, eax
0x18002612e  jnz     short loc_18002614E
0x180026130  call    cs:__imp_GetLastError
0x180026136  mov     ebx, eax
0x180026138  test    eax, eax
0x18002613a  jle     loc_1800263F7
0x180026140  movzx   ebx, ax
0x180026143  or      ebx, 80070000h
0x180026149  jmp     loc_1800263F7
0x18002614e  xorps   xmm0, xmm0
0x180026151  mov     [rsp+970h+string], rsi
0x180026156  xor     eax, eax
0x180026158  mov     dword ptr [rbp+870h+var_6F0.Ptr], esi
0x18002615e  mov     ecx, 208h; unsigned __int64
0x180026163  mov     [rbp+870h+var_6AC], eax
0x180026169  movups  xmmword ptr [rbp+870h+var_6F0.Ptr+4], xmm0
0x180026170  movups  [rbp+870h+var_6DC], xmm0
0x180026177  movups  [rbp+870h+var_6CC], xmm0
0x18002617e  movups  [rbp+870h+var_6BC], xmm0
0x180026185  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002618a  mov     rdx, rax; unsigned __int16 *
0x18002618d  mov     rcx, rbx; hMonitor
0x180026190  mov     rdi, rax
0x180026193  call    ?InternalTranslateHMonitorToICMName@@YAJPEAUHMONITOR__@@PEAG@Z; InternalTranslateHMonitorToICMName(HMONITOR__ *,ushort *)
0x180026198  mov     ebx, eax
0x18002619a  test    eax, eax
0x18002619c  js      loc_18002622D
0x1800261a2  lea     rdx, [rbp+870h+var_6F0]; struct DISPLAYCONFIG_PATH_INFO *
0x1800261a9  mov     rcx, rdi; unsigned __int16 *
0x1800261ac  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x1800261b1  mov     ebx, eax
0x1800261b3  test    eax, eax
0x1800261b5  js      short loc_18002622D
0x1800261b7  xor     edx, edx; Val
0x1800261b9  lea     rcx, [rbp+870h+var_88C]; void *
0x1800261bd  mov     r8d, 190h; Size
0x1800261c3  call    memset_0
0x1800261c8  mov     rax, qword ptr [rbp+870h+var_6DC]
0x1800261cf  lea     rcx, [rbp+870h+requestPacket]; requestPacket
0x1800261d3  mov     qword ptr [rbp+870h+requestPacket.adapterId.LowPart], rax
0x1800261d7  mov     eax, dword ptr [rbp+870h+var_6DC+8]
0x1800261dd  mov     [rbp+870h+requestPacket.id], eax
0x1800261e0  mov     [rbp+870h+requestPacket.type], 2
0x1800261e7  mov     [rbp+870h+requestPacket.size], 1A4h
0x1800261ee  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800261f4  test    eax, eax
0x1800261f6  jle     short loc_180026202
0x1800261f8  movzx   eax, ax
0x1800261fb  or      eax, 80070000h
0x180026200  test    eax, eax
0x180026202  js      loc_1800263F2
0x180026208  lea     rax, [rbp+870h+sourceString]
0x18002620c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180026213  inc     rdx; length
0x180026216  cmp     [rax+rdx*2], si
0x18002621a  jnz     short loc_180026213
0x18002621c  lea     r8, [rsp+970h+string]; string
0x180026221  lea     rcx, [rbp+870h+sourceString]; sourceString
0x180026225  call    cs:__imp_WindowsCreateString
0x18002622b  mov     ebx, eax
0x18002622d  test    ebx, ebx
0x18002622f  js      loc_1800263F7
0x180026235  mov     [rsp+970h+var_28], r13
0x18002623d  mov     rbx, rsi
0x180026240  movaps  [rsp+970h+var_58+8], xmm6
0x180026248  mov     r13d, esi
0x18002624b  movaps  [rsp+970h+var_68+8], xmm7
0x180026253  movaps  [rsp+970h+var_78+8], xmm8
0x18002625c  movss   xmm8, cs:__real@437f0000
0x180026265  movaps  [rsp+970h+var_88+8], xmm9
0x18002626e  movss   xmm9, cs:__real@3f800000
0x180026277  movaps  [rsp+970h+var_98+8], xmm10
0x180026280  movss   xmm10, cs:__real@3f000000
0x180026289  mov     [rsp+970h+var_940], rbx
0x18002628e  xchg    ax, ax
0x180026290  xorps   xmm7, xmm7
0x180026293  mov     eax, r13d
0x180026296  mov     rcx, r14
0x180026299  cvtsi2ss xmm7, rax
0x18002629e  mov     rax, [r14]
0x1800262a1  mov     rax, [rax]
0x1800262a4  divss   xmm7, xmm8
0x1800262a9  movaps  xmm1, xmm7
0x1800262ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262b1  mov     rax, [r15]
0x1800262b4  xorps   xmm1, xmm1
0x1800262b7  maxss   xmm1, xmm0
0x1800262bb  movaps  xmm6, xmm9
0x1800262bf  mov     rcx, r15
0x1800262c2  mov     rax, [rax]
0x1800262c5  minss   xmm6, xmm1
0x1800262c9  movaps  xmm1, xmm7
0x1800262cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262d1  mov     rax, [r12]
0x1800262d5  lea     rsi, [rbx+rbx*2]
0x1800262d9  xorps   xmm1, xmm1
0x1800262dc  mulss   xmm6, xmm8
0x1800262e1  mov     rcx, r12
0x1800262e4  maxss   xmm1, xmm0
0x1800262e8  movaps  xmm2, xmm9
0x1800262ec  mov     rax, [rax]
0x1800262ef  addss   xmm6, xmm10
0x1800262f4  minss   xmm2, xmm1
0x1800262f8  movaps  xmm1, xmm7
0x1800262fb  cvttss2si edi, xmm6
0x1800262ff  mulss   xmm2, xmm8
0x180026304  shl     di, 8
0x180026308  addss   xmm2, xmm10
0x18002630d  cvttss2si ebx, xmm2
0x180026311  shl     bx, 8
0x180026315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002631a  xorps   xmm1, xmm1
0x18002631d  movaps  xmm2, xmm9
0x180026321  maxss   xmm1, xmm0
0x180026325  movzx   eax, di
0x180026328  ror     ax, 8
0x18002632c  inc     r13d
0x18002632f  add     ax, di
0x180026332  mov     [rbp+rsi*2+870h+var_6A0], ax
0x18002633a  movzx   eax, bx
0x18002633d  ror     ax, 8
0x180026341  add     ax, bx
0x180026344  minss   xmm2, xmm1
0x180026348  mov     rbx, [rsp+970h+var_940]
0x18002634d  mov     [rbp+rsi*2+870h+var_69E], ax
0x180026355  inc     rbx
0x180026358  mov     [rsp+970h+var_940], rbx
0x18002635d  mulss   xmm2, xmm8
0x180026362  addss   xmm2, xmm10
0x180026367  cvttss2si ecx, xmm2
0x18002636b  shl     cx, 8
0x18002636f  movzx   eax, cx
0x180026372  ror     ax, 8
0x180026376  add     ax, cx
0x180026379  mov     [rbp+rsi*2+870h+var_69C], ax
0x180026381  cmp     r13d, 100h
0x180026388  jb      loc_180026290
0x18002638e  movups  xmm0, cs:xmmword_18008C718
0x180026395  mov     rcx, [rsp+970h+string]; HSTRING
0x18002639a  lea     r8, [rbp+870h+var_6A0]; struct UINT16Triple (*)[256]
0x1800263a1  movaps  xmm10, [rsp+970h+var_98+8]
0x1800263aa  lea     rdx, [rsp+970h+EventDescriptor.Keyword]; struct _GUID
0x1800263af  movaps  xmm9, [rsp+970h+var_88+8]
0x1800263b8  movaps  xmm8, [rsp+970h+var_78+8]
0x1800263c1  movaps  xmm7, [rsp+970h+var_68+8]
0x1800263c9  movaps  xmm6, [rsp+970h+var_58+8]
0x1800263d1  mov     r13, [rsp+970h+var_28]
0x1800263d9  movaps  xmmword ptr [rsp+970h+EventDescriptor.Keyword], xmm0
0x1800263de  call    ?ModernColorSetGDILut@@YAJPEAUHSTRING__@@U_GUID@@AEAY0BAA@UUINT16Triple@@@Z; ModernColorSetGDILut(HSTRING__ *,_GUID,UINT16Triple (&)[256])
0x1800263e3  mov     rcx, [rsp+970h+string]; string
0x1800263e8  mov     ebx, eax
0x1800263ea  call    cs:__imp_WindowsDeleteString
0x1800263f0  jmp     short loc_1800263F7
0x1800263f2  mov     ebx, 80070057h
0x1800263f7  mov     eax, cs:dword_18009E048
0x1800263fd  mov     r15, [rsp+970h+var_38]
0x180026405  mov     r14, [rsp+970h+var_30]
0x18002640d  mov     r12, [rsp+970h+var_20]
0x180026415  mov     rdi, [rsp+958h]
0x18002641d  cmp     eax, 5
0x180026420  jbe     loc_180026509
0x180026426  mov     rcx, cs:qword_18009E060
0x18002642d  mov     rax, cs:qword_18009E058
0x180026434  test    al, 1
0x180026436  jz      loc_180026509
0x18002643c  mov     rax, rcx
0x18002643f  and     eax, 1
0x180026442  cmp     rax, rcx
0x180026445  jnz     loc_180026509
0x18002644b  lea     rax, [rsp+970h+var_938]
0x180026450  mov     dword ptr [rsp+970h+var_938], ebx
0x180026454  mov     qword ptr [rbp+870h+var_6DC+0Ch], rax
0x18002645b  lea     rcx, _TraceLoggingMetadata
0x180026462  movzx   eax, cs:word_1800920E7
0x180026469  lea     rdx, [rsp+970h+EventDescriptor.Keyword]; EventDescriptor
0x18002646e  mov     dword ptr [rsp+970h+EventDescriptor.Keyword+4], eax
0x180026472  xor     r9d, r9d; RelatedActivityId
0x180026475  mov     rax, cs:off_18009E050
0x18002647c  xor     r8d, r8d; ActivityId
0x18002647f  mov     [rbp+870h+var_6F0.Ptr], rax
0x180026486  mov     qword ptr [rbp+870h+var_6CC+4], 4
0x180026491  mov     dword ptr [rsp+970h+EventDescriptor.Keyword], 0B000000h
0x180026499  mov     qword ptr [rsp+970h+var_918], 1
0x1800264a2  movzx   eax, word ptr [rax]
0x1800264a5  mov     [rbp+870h+var_6F0.Size], eax
0x1800264ab  lea     rax, byte_1800920F1
0x1800264b2  mov     [rbp+190h], rax
0x1800264b9  lea     rax, _TraceLoggingMetadataEnd
0x1800264c0  sub     eax, ecx
0x1800264c2  mov     dword ptr [rbp+870h+var_6F0.0Ch], 2
0x1800264cc  mov     dword ptr [rbp+870h+var_6DC+4], 31h ; '1'
0x1800264d6  mov     dword ptr [rbp+870h+var_6DC+8], 1
0x1800264e0  mov     dword ptr [rsp+970h+var_940], eax
0x1800264e4  mov     eax, dword ptr [rsp+970h+var_940]
0x1800264e8  mov     rcx, cs:qword_18009E068; RegHandle
0x1800264ef  lea     rax, [rbp+870h+var_6F0]
0x1800264f6  mov     [rsp+970h+UserData], rax; UserData
0x1800264fb  mov     [rsp+970h+UserDataCount], 3; UserDataCount
0x180026503  call    cs:__imp_EventWriteTransfer
0x180026509  xor     ecx, ecx; void *
0x18002650b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026510  mov     eax, ebx
0x180026512  mov     rcx, [rbp+870h+var_A0]
0x180026519  xor     rcx, rsp; StackCookie
0x18002651c  call    __security_check_cookie
0x180026521  add     rsp, 960h
0x180026528  pop     rsi
0x180026529  pop     rbx
0x18002652a  pop     rbp
0x18002652b  retn
```
