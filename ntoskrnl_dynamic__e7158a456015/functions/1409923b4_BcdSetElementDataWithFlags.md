# BcdSetElementDataWithFlags

- ea: `0x1409923b4`
- end: `0x140992654`
- name: `BcdSetElementDataWithFlags`
- size: `672`
- prototype: ``
- caller_count: `10`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1407a3e94`
- `0x1407a41a8`
- `0x1407cb4e4`
- `0x140831f3c`
- `0x140990054`
- `0x140991f50`
- `0x1409922b0`
- `0x140992394`
- `0x140993910`
- `0x140ae9810`

## callees

- `0x140549550`
- `0x1406dc8c0`
- `0x14098f710`
- `0x140991068`
- `0x1409910a0`
- `0x1409913a0`
- `0x1409923b4`
- `0x140992e34`
- `0x140993038`
- `0x1409934f0`
- `0x140993654`
- `0x140993780`
- `0x1409937e0`
- `0x14099487c`
- `0x140994f7c`
- `0x140995510`
- `0x140bb19f0`

## string_xrefs

- `0x1409925fa`: `Failed to set registry data for element %s. Status: %x`
- `0x1409925d7`: `Failed to open key for element %s. Status: %x`
- `0x140992584`: `Failed to open key for object's elements. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdSetElementDataWithFlags(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  HANDLE v7; // rdi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  PVOID v15; // r15
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v19; // r8d
  int *v20; // [rsp+28h] [rbp-59h]
  _BYTE v21[4]; // [rsp+30h] [rbp-51h] BYREF
  int v22; // [rsp+34h] [rbp-4Dh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-41h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-39h] BYREF
  PVOID P; // [rsp+50h] [rbp-31h]
  __int64 v27; // [rsp+58h] [rbp-29h]
  wchar_t DstBuf[24]; // [rsp+60h] [rbp-21h] BYREF

  v27 = a4;
  v24 = a2;
  v22 = 0;
  if ( !a4 && a5 )
    return 3221225485LL;
  v23 = 0;
  v7 = 0;
  v21[0] = 0;
  Handle = 0;
  P = 0;
  if ( !a5 )
  {
    BiDeleteElement(a1, a2);
    return 0;
  }
  BiLogMessage(2, L"Setting element %08x", a2);
  LOBYTE(v8) = a1 & 1;
  v9 = BiAcquireBcdSyncMutant(v8);
  if ( v9 < 0 )
  {
    BiLogMessage(4, L"BcdSetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v9);
    return v19;
  }
  v10 = BiOpenKey(a1, L"Elements", 131101, &v23);
  v11 = v10;
  if ( v10 < 0 )
  {
    BiLogMessage(4, L"Failed to open key for object's elements. Status: %x", (unsigned int)v10);
    goto LABEL_22;
  }
  if ( !ultow_s(a2, DstBuf, 0x16u, 16) )
  {
    v13 = BiCreateKey(v23, DstBuf, 65538, 1, &Handle, v21);
    v11 = v13;
    if ( v13 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for element %s. Status: %x", DstBuf, (unsigned int)v13);
      v7 = Handle;
    }
    else
    {
      v20 = &v22;
      v14 = BiConvertElementToRegistryData(a2, v27, a5);
      v7 = Handle;
      v11 = v14;
      v15 = P;
      if ( v14 < 0 )
      {
        BiLogMessage(4, L"Failed to convert data for element %s. Status: %x", DstBuf, (unsigned int)v14);
      }
      else
      {
        v16 = BiConvertElementFormatToValueType(HIBYTE(a2) & 0xF);
        LODWORD(v20) = v22;
        v17 = BiSetRegistryValue(v7, L"Element", 0, v16, v15, v20);
        v11 = v17;
        if ( v17 < 0 )
          BiLogMessage(4, L"Failed to set registry data for element %s. Status: %x", DstBuf, (unsigned int)v17);
      }
      if ( v15 )
        ExFreePoolWithTag(v15, 0x4B444342u);
      if ( v11 >= 0 )
        goto LABEL_13;
    }
LABEL_22:
    if ( v21[0] )
    {
      BiDeleteKey(v7);
      v7 = 0;
    }
LABEL_13:
    if ( v7 )
      BiCloseKey(v7);
    goto LABEL_15;
  }
  v11 = -1073741823;
LABEL_15:
  if ( v23 )
    BiCloseKey(v23);
  if ( v11 >= 0 )
  {
    if ( (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v24) )
      BiSetFirmwareModifiedFromObject(a1);
  }
  LOBYTE(v12) = a1 & 1;
  BiReleaseBcdSyncMutant(v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1409923b4  push    rbp
0x1409923b6  push    rbx
0x1409923b7  push    rsi
0x1409923b8  push    rdi
0x1409923b9  push    r13
0x1409923bb  push    r14
0x1409923bd  push    r15
0x1409923bf  lea     rbp, [rsp-1Fh]
0x1409923c4  sub     rsp, 0A0h
0x1409923cb  mov     rax, cs:__security_cookie
0x1409923d2  xor     rax, rsp
0x1409923d5  mov     [rbp+4Fh+var_40], rax
0x1409923d9  mov     r15d, [rbp+4Fh+arg_20]
0x1409923dd  xor     ebx, ebx
0x1409923df  mov     [rbp+4Fh+var_78], r9
0x1409923e3  mov     esi, edx
0x1409923e5  mov     [rbp+4Fh+var_90], edx
0x1409923e8  mov     r14, rcx
0x1409923eb  mov     [rbp+4Fh+var_9C], ebx
0x1409923ee  test    r9, r9
0x1409923f1  jz      loc_140992571
0x1409923f7  mov     [rbp+4Fh+var_98], rbx
0x1409923fb  mov     rdi, rbx
0x1409923fe  mov     [rbp+4Fh+var_A0], bl
0x140992401  mov     [rbp+4Fh+Handle], rbx
0x140992405  mov     [rbp+4Fh+P], rbx
0x140992409  test    r15d, r15d
0x14099240c  jz      loc_1409925A7
0x140992412  mov     r8d, esi
0x140992415  lea     rdx, aSettingElement; "Setting element %08x"
0x14099241c  mov     ecx, 2
0x140992421  call    BiLogMessage
0x140992426  mov     r13b, r14b
0x140992429  and     r13b, 1
0x14099242d  mov     cl, r13b
0x140992430  call    BiAcquireBcdSyncMutant
0x140992435  mov     r8d, eax
0x140992438  test    eax, eax
0x14099243a  js      loc_1409925B0
0x140992440  lea     r9, [rbp+4Fh+var_98]
0x140992444  mov     r8d, 2001Dh
0x14099244a  lea     rdx, aElements; "Elements"
0x140992451  mov     rcx, r14
0x140992454  call    BiOpenKey
0x140992459  mov     ebx, eax
0x14099245b  test    eax, eax
0x14099245d  js      loc_140992581
0x140992463  mov     r9d, 10h; Radix
0x140992469  lea     rdx, [rbp+4Fh+DstBuf]; DstBuf
0x14099246d  mov     ecx, esi; Val
0x14099246f  lea     r8d, [r9+6]; SizeInWords
0x140992473  call    _ultow_s
0x140992478  test    eax, eax
0x14099247a  jnz     loc_1409925C6
0x140992480  mov     rcx, [rbp+4Fh+var_98]
0x140992484  lea     rax, [rbp+4Fh+var_A0]
0x140992488  mov     [rsp+0D0h+var_A8], rax
0x14099248d  lea     rdx, [rbp+4Fh+DstBuf]
0x140992491  lea     rax, [rbp+4Fh+Handle]
0x140992495  mov     r9d, 1
0x14099249b  mov     r8d, 10002h
0x1409924a1  mov     [rsp+0D0h+var_B0], rax
0x1409924a6  call    BiCreateKey
0x1409924ab  mov     ebx, eax
0x1409924ad  test    eax, eax
0x1409924af  js      loc_1409925D0
0x1409924b5  mov     rdx, [rbp+4Fh+var_78]
0x1409924b9  lea     rax, [rbp+4Fh+var_9C]
0x1409924bd  mov     [rsp+0D0h+var_A8], rax
0x1409924c2  mov     r8d, r15d
0x1409924c5  lea     rax, [rbp+4Fh+P]
0x1409924c9  mov     ecx, esi
0x1409924cb  mov     [rsp+0D0h+var_B0], rax
0x1409924d0  call    BiConvertElementToRegistryData
0x1409924d5  mov     rdi, [rbp+4Fh+Handle]
0x1409924d9  mov     ebx, eax
0x1409924db  mov     r15, [rbp+4Fh+P]
0x1409924df  test    eax, eax
0x1409924e1  js      loc_1409925EE
0x1409924e7  shr     esi, 18h
0x1409924ea  and     esi, 0Fh
0x1409924ed  mov     ecx, esi
0x1409924ef  call    BiConvertElementFormatToValueType
0x1409924f4  mov     r9d, eax
0x1409924f7  lea     rdx, aElement; "Element"
0x1409924fe  mov     eax, [rbp+4Fh+var_9C]
0x140992501  xor     r8d, r8d
0x140992504  mov     dword ptr [rsp+0D0h+var_A8], eax
0x140992508  mov     rcx, rdi
0x14099250b  mov     [rsp+0D0h+var_B0], r15
0x140992510  call    BiSetRegistryValue
0x140992515  mov     ebx, eax
0x140992517  test    eax, eax
0x140992519  js      loc_1409925FA
0x14099251f  test    r15, r15
0x140992522  jnz     loc_140992606
0x140992528  test    ebx, ebx
0x14099252a  js      short loc_140992595
0x14099252c  test    rdi, rdi
0x14099252f  jnz     loc_140992618
0x140992535  cmp     [rbp+4Fh+var_98], 0
0x14099253a  jnz     loc_140992625
0x140992540  test    ebx, ebx
0x140992542  jns     loc_140992633
0x140992548  mov     cl, r13b
0x14099254b  call    BiReleaseBcdSyncMutant
0x140992550  mov     eax, ebx
0x140992552  mov     rcx, [rbp+4Fh+var_40]
0x140992556  xor     rcx, rsp; StackCookie
0x140992559  call    __security_check_cookie
0x14099255e  add     rsp, 0A0h
0x140992565  pop     r15
0x140992567  pop     r14
0x140992569  pop     r13
0x14099256b  pop     rdi
0x14099256c  pop     rsi
0x14099256d  pop     rbx
0x14099256e  pop     rbp
0x14099256f  retn
0x140992571  test    r15d, r15d
0x140992574  jz      loc_1409923F7
0x14099257a  mov     eax, 0C000000Dh
0x14099257f  jmp     short loc_140992552
0x140992581  mov     r8d, eax
0x140992584  lea     rdx, aFailedToOpenKe_2; "Failed to open key for object's element"...
0x14099258b  mov     ecx, 4
0x140992590  call    BiLogMessage
0x140992595  cmp     [rbp+4Fh+var_A0], 0
0x140992599  jz      short loc_14099252C
0x14099259b  mov     rcx, rdi
0x14099259e  call    BiDeleteKey
0x1409925a3  xor     edi, edi
0x1409925a5  jmp     short loc_14099252C
0x1409925a7  call    BiDeleteElement
0x1409925ac  xor     eax, eax
0x1409925ae  jmp     short loc_140992552
0x1409925b0  lea     rdx, aBcdsetelementd; "BcdSetElementDataWithFlags: Failed to a"...
0x1409925b7  mov     ecx, 4
0x1409925bc  call    BiLogMessage
0x1409925c1  mov     eax, r8d
0x1409925c4  jmp     short loc_140992552
0x1409925c6  mov     ebx, 0C0000001h
0x1409925cb  jmp     loc_140992535
0x1409925d0  mov     r9d, eax
0x1409925d3  lea     r8, [rbp+4Fh+DstBuf]
0x1409925d7  lea     rdx, aFailedToOpenKe_3; "Failed to open key for element %s. Stat"...
0x1409925de  mov     ecx, 4
0x1409925e3  call    BiLogMessage
0x1409925e8  mov     rdi, [rbp+4Fh+Handle]
0x1409925ec  jmp     short loc_140992595
0x1409925ee  lea     rdx, aFailedToConver_3; "Failed to convert data for element %s. "...
0x1409925f5  jmp     loc_140B6338C
0x1409925fa  lea     rdx, aFailedToSetReg; "Failed to set registry data for element"...
0x140992601  jmp     loc_140B6338C
0x140992606  mov     edx, 4B444342h; Tag
0x14099260b  mov     rcx, r15; P
0x14099260e  call    ExFreePoolWithTag
0x140992613  jmp     loc_140992528
0x140992618  mov     rcx, rdi; Handle
0x14099261b  call    BiCloseKey
0x140992620  jmp     loc_140992535
0x140992625  mov     rcx, [rbp+4Fh+var_98]; Handle
0x140992629  call    BiCloseKey
0x14099262e  jmp     loc_140992540
0x140992633  lea     rdx, [rbp+4Fh+var_90]
0x140992637  mov     rcx, r14
0x14099263a  call    BiIsLinkedToFirmwareVariable
0x14099263f  test    al, al
0x140992641  jz      loc_140992548
0x140992647  mov     rcx, r14
0x14099264a  call    BiSetFirmwareModifiedFromObject
0x14099264f  jmp     loc_140992548
0x140b6338c  mov     r9d, eax
0x140b6338f  lea     r8, [rbp+4Fh+DstBuf]
0x140b63393  mov     ecx, 4
0x140b63398  call    BiLogMessage
0x140b6339d  nop
0x140b6339e  jmp     loc_14099251F
```
