# HsmiPrepareBitmapCommit

- ea: `0x140067854`
- end: `0x1400679e3`
- name: `HsmiPrepareBitmapCommit`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140067d04`

## callees

- `0x140003c50`
- `0x140009300`
- `0x140058cbc`
- `0x140065c84`
- `0x140067854`
- `0x1400697c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400679d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400679d2`
- `ntoskrnl!ExAllocatePool2` at `0x1400678c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400678c8`

## pseudocode

```c
__int64 __fastcall HsmiPrepareBitmapCommit(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  __int64 v4; // r15
  __int64 Bitmap; // rbx
  _DWORD *v9; // r9
  __int64 StreamSize; // r12
  void *Pool2; // rdi
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 16);
  Bitmap = HsmiGetBitmap(a1, a2, 0);
  StreamSize = HsmpGetStreamSize(a1);
  LODWORD(v13) = 5120;
  if ( Bitmap )
  {
    Pool2 = (void *)ExAllocatePool2(256, 5120, 1884451656);
    if ( Pool2 )
    {
      if ( (*(_DWORD *)(Bitmap + 16) & 7) != 0 )
        LODWORD(Bitmap) = -1073741595;
      else
        LODWORD(Bitmap) = HsmIBitmapNORMALPrepareCommit(Bitmap, StreamSize, 0, (__int64)Pool2, &v13);
      HsmDbgBreakOnStatus((unsigned int)Bitmap);
      if ( (int)Bitmap < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
            a1,
            *(_QWORD *)(v4 + 32),
            Bitmap);
        }
        ExFreePoolWithTag(Pool2, 0x70527348u);
      }
      else
      {
        *a4 = v13;
        *a3 = Pool2;
      }
    }
    else
    {
      LODWORD(Bitmap) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
          a1,
          *(_QWORD *)(v4 + 32),
          -1073741670);
      }
    }
  }
  else
  {
    *a3 = 0;
    *v9 = 0;
  }
  return (unsigned int)Bitmap;
}

```

## disassembly

```asm
0x140067854  mov     [rsp+arg_8], rbx
0x140067859  mov     [rsp+arg_10], rbp
0x14006785e  push    rsi
0x14006785f  push    rdi
0x140067860  push    r12
0x140067862  push    r14
0x140067864  push    r15
0x140067866  sub     rsp, 40h
0x14006786a  mov     r15, [rcx+10h]
0x14006786e  mov     r14, r8
0x140067871  xor     r8d, r8d
0x140067874  mov     rsi, r9
0x140067877  mov     rbp, rcx
0x14006787a  call    HsmiGetBitmap
0x14006787f  mov     rcx, rbp
0x140067882  mov     rbx, rax
0x140067885  call    HsmpGetStreamSize
0x14006788a  mov     edx, 1400h
0x14006788f  mov     r12, rax
0x140067892  mov     dword ptr [rsp+68h+arg_0], edx
0x140067896  test    rbx, rbx
0x140067899  jnz     short loc_1400678BD
0x14006789b  mov     [r14], rbx
0x14006789e  mov     [r9], ebx
0x1400678a1  lea     r11, [rsp+68h+var_28]
0x1400678a6  mov     eax, ebx
0x1400678a8  mov     rbx, [r11+38h]
0x1400678ac  mov     rbp, [r11+40h]
0x1400678b0  mov     rsp, r11
0x1400678b3  pop     r15
0x1400678b5  pop     r14
0x1400678b7  pop     r12
0x1400678b9  pop     rdi
0x1400678ba  pop     rsi
0x1400678bb  retn
0x1400678bd  mov     ecx, 100h
0x1400678c2  mov     r8d, 70527348h
0x1400678c8  call    cs:__imp_ExAllocatePool2
0x1400678cf  nop     dword ptr [rax+rax+00h]
0x1400678d4  mov     rdi, rax
0x1400678d7  test    rax, rax
0x1400678da  jz      short loc_14006791C
0x1400678dc  test    dword ptr [rbx+10h], 7
0x1400678e3  jnz     loc_14006797E
0x1400678e9  lea     rax, [rsp+68h+arg_0]
0x1400678ee  mov     r9, rdi
0x1400678f1  xor     r8d, r8d
0x1400678f4  mov     [rsp+68h+var_48], rax; __int64
0x1400678f9  mov     rdx, r12
0x1400678fc  mov     rcx, rbx; int
0x1400678ff  call    HsmIBitmapNORMALPrepareCommit
0x140067904  mov     ebx, eax
0x140067906  mov     ecx, ebx
0x140067908  call    HsmDbgBreakOnStatus
0x14006790d  test    ebx, ebx
0x14006790f  js      short loc_140067985
0x140067911  mov     ecx, dword ptr [rsp+68h+arg_0]
0x140067915  mov     [rsi], ecx
0x140067917  mov     [r14], rdi
0x14006791a  jmp     short loc_1400678A1
0x14006791c  mov     ebx, 0C000009Ah
0x140067921  mov     ecx, ebx
0x140067923  call    HsmDbgBreakOnStatus
0x140067928  mov     rcx, cs:WPP_GLOBAL_Control
0x14006792f  lea     rax, WPP_GLOBAL_Control
0x140067936  cmp     rcx, rax
0x140067939  jz      loc_1400678A1
0x14006793f  mov     eax, [rcx+2Ch]
0x140067942  test    al, 1
0x140067944  jz      loc_1400678A1
0x14006794a  cmp     byte ptr [rcx+29h], 2
0x14006794e  jb      loc_1400678A1
0x140067954  mov     rax, [r15+20h]
0x140067958  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x14006795f  mov     rcx, [rcx+18h]
0x140067963  mov     edx, 18h
0x140067968  mov     [rsp+68h+var_40], ebx
0x14006796c  mov     r9, rbp
0x14006796f  mov     [rsp+68h+var_48], rax
0x140067974  call    WPP_SF_qqd
0x140067979  jmp     loc_1400678A1
0x14006797e  mov     ebx, 0C00000E5h
0x140067983  jmp     short loc_140067906
0x140067985  mov     rcx, cs:WPP_GLOBAL_Control
0x14006798c  lea     rax, WPP_GLOBAL_Control
0x140067993  cmp     rcx, rax
0x140067996  jz      short loc_1400679CA
0x140067998  mov     eax, [rcx+2Ch]
0x14006799b  test    al, 1
0x14006799d  jz      short loc_1400679CA
0x14006799f  cmp     byte ptr [rcx+29h], 2
0x1400679a3  jb      short loc_1400679CA
0x1400679a5  mov     rax, [r15+20h]
0x1400679a9  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x1400679b0  mov     rcx, [rcx+18h]
0x1400679b4  mov     edx, 19h
0x1400679b9  mov     [rsp+68h+var_40], ebx
0x1400679bd  mov     r9, rbp
0x1400679c0  mov     [rsp+68h+var_48], rax
0x1400679c5  call    WPP_SF_qqd
0x1400679ca  mov     edx, 70527348h; Tag
0x1400679cf  mov     rcx, rdi; P
0x1400679d2  call    cs:__imp_ExFreePoolWithTag
0x1400679d9  nop     dword ptr [rax+rax+00h]
0x1400679de  jmp     loc_1400678A1
```
