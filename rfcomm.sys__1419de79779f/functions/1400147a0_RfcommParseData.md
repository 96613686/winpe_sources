# RfcommParseData

- ea: `0x1400147a0`
- end: `0x1400149ab`
- name: `RfcommParseData`
- size: `523`
- prototype: `void __fastcall(__int64, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ebe0`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14000ca20`
- `0x14001127c`
- `0x14001138c`
- `0x140012590`
- `0x14001291c`
- `0x140012c60`
- `0x1400147a0`
- `0x140015b04`
- `0x140016738`
- `0x1400168e8`
- `0x14001699c`
- `0x14001bfa8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140014963`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014963`

## pseudocode

```c
void __fastcall RfcommParseData(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v5; // rbp
  void *DeviceExtension; // rbx
  __int64 v10; // rax
  int v11; // edx
  char v12; // bl
  int v13; // edx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  int v17; // edx

  v5 = a2 - 32;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v10 = NtStatusTxt((unsigned int)a4);
    WPP_RECORDER_SF_qqs(
      (_DWORD)DeviceExtension,
      v11,
      3,
      163,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1,
      v5,
      v10);
  }
  if ( a4 >= 0 )
  {
    *(_DWORD *)(v5 + 20) = a3;
    *(_DWORD *)(v5 + 28) = a3;
    v12 = 1;
    if ( (unsigned __int8)ValidateFrameHeader(a1, a2, a3) )
    {
      if ( (*(_BYTE *)(a2 + 1) & 0xEF) == 0xEF )
      {
        if ( (unsigned __int8)ValidateUIHFrame(a1, a2, a3) )
        {
          v12 = HandleUIHFrame(a1, v5, v14, v15);
          goto LABEL_17;
        }
      }
      else if ( (unsigned __int8)ValidateBasicFrame(a1, a2) )
      {
        v16 = *(_BYTE *)(a2 + 1) & 0xEF;
        switch ( v16 )
        {
          case 15:
            HandleDMFrame(a1, a2);
            goto LABEL_17;
          case 47:
            HandleSABMFrame(a1, a2);
            goto LABEL_17;
          case 67:
            HandleDISCFrame(a1, a2);
            goto LABEL_17;
          case 99:
            HandleUAFrame(a1, a2);
            goto LABEL_17;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_17:
          RfcommStartRead(a1, v5 & -(__int64)(v12 != 0));
          goto LABEL_25;
        }
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          11,
          164,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          *(_BYTE *)(a2 + 1));
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        1,
        165,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    goto LABEL_17;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      2,
      166,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  ExFreePoolWithTag((PVOID)v5, 0);
LABEL_25:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      3,
      167,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
}

```

## disassembly

```asm
0x1400147a0  push    rbx
0x1400147a2  push    rbp
0x1400147a3  push    rsi
0x1400147a4  push    rdi
0x1400147a5  push    r12
0x1400147a7  push    r13
0x1400147a9  push    r14
0x1400147ab  push    r15
0x1400147ad  sub     rsp, 48h
0x1400147b1  mov     r15d, r9d
0x1400147b4  lea     rbp, [rdx-20h]
0x1400147b8  mov     r14d, r8d
0x1400147bb  mov     rdi, rdx
0x1400147be  mov     rsi, rcx
0x1400147c1  lea     r12, WPP_RECORDER_INITIALIZED
0x1400147c8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400147cf  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400147d6  jz      short loc_140014813
0x1400147d8  mov     rax, cs:WPP_GLOBAL_Control
0x1400147df  mov     ecx, r9d
0x1400147e2  mov     rbx, [rax+40h]
0x1400147e6  call    NtStatusTxt
0x1400147eb  mov     [rsp+88h+var_50], rax
0x1400147f0  mov     r9d, 0A3h
0x1400147f6  mov     [rsp+88h+var_58], rbp
0x1400147fb  mov     r8d, 3
0x140014801  mov     [rsp+88h+var_60], rsi
0x140014806  mov     rcx, rbx
0x140014809  mov     [rsp+88h+var_68], r13
0x14001480e  call    WPP_RECORDER_SF_qqs
0x140014813  test    r15d, r15d
0x140014816  js      loc_140014934
0x14001481c  mov     r8d, r14d
0x14001481f  mov     [rbp+14h], r14d
0x140014823  mov     rdx, rdi
0x140014826  mov     [rbp+1Ch], r14d
0x14001482a  mov     ebx, 1
0x14001482f  call    ValidateFrameHeader
0x140014834  test    al, al
0x140014836  jz      loc_1400148C7
0x14001483c  movzx   eax, byte ptr [rdi+1]
0x140014840  mov     rdx, rdi
0x140014843  and     eax, 0FFFFFFEFh
0x140014846  mov     rcx, rsi
0x140014849  cmp     al, 0EFh
0x14001484b  jnz     short loc_14001486B
0x14001484d  mov     r8d, r14d
0x140014850  call    ValidateUIHFrame
0x140014855  test    al, al
0x140014857  jz      short loc_1400148C7
0x140014859  mov     rdx, rbp
0x14001485c  mov     rcx, rsi
0x14001485f  call    HandleUIHFrame
0x140014864  mov     bl, al
0x140014866  jmp     loc_1400148EE
0x14001486b  call    ValidateBasicFrame
0x140014870  test    al, al
0x140014872  jz      short loc_1400148C7
0x140014874  movzx   ecx, byte ptr [rdi+1]
0x140014878  mov     eax, ecx
0x14001487a  and     eax, 0FFFFFFEFh
0x14001487d  cmp     eax, 0Fh
0x140014880  jz      loc_140014927
0x140014886  cmp     eax, 2Fh ; '/'
0x140014889  jz      loc_14001491A
0x14001488f  cmp     eax, 43h ; 'C'
0x140014892  jz      short loc_14001490D
0x140014894  cmp     eax, 63h ; 'c'
0x140014897  jz      short loc_140014900
0x140014899  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400148a0  jz      short loc_1400148EE
0x1400148a2  mov     dword ptr [rsp+88h+var_60], ecx
0x1400148a6  mov     r9d, 0A4h
0x1400148ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148b3  mov     r8d, 0Bh
0x1400148b9  mov     [rsp+88h+var_68], r13
0x1400148be  mov     rcx, [rcx+40h]
0x1400148c2  call    WPP_RECORDER_SF_d
0x1400148c7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400148ce  jz      short loc_1400148EE
0x1400148d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148d7  mov     r9d, 0A5h
0x1400148dd  mov     r8d, ebx
0x1400148e0  mov     [rsp+88h+var_68], r13
0x1400148e5  mov     rcx, [rcx+40h]
0x1400148e9  call    WPP_RECORDER_SF_
0x1400148ee  neg     bl
0x1400148f0  mov     rcx, rsi
0x1400148f3  sbb     rdx, rdx
0x1400148f6  and     rdx, rbp
0x1400148f9  call    RfcommStartRead
0x1400148fe  jmp     short loc_14001496F
0x140014900  mov     rdx, rdi
0x140014903  mov     rcx, rsi
0x140014906  call    HandleUAFrame
0x14001490b  jmp     short loc_1400148EE
0x14001490d  mov     rdx, rdi
0x140014910  mov     rcx, rsi
0x140014913  call    HandleDISCFrame
0x140014918  jmp     short loc_1400148EE
0x14001491a  mov     rdx, rdi
0x14001491d  mov     rcx, rsi
0x140014920  call    HandleSABMFrame
0x140014925  jmp     short loc_1400148EE
0x140014927  mov     rdx, rdi
0x14001492a  mov     rcx, rsi
0x14001492d  call    HandleDMFrame
0x140014932  jmp     short loc_1400148EE
0x140014934  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001493b  jz      short loc_14001495E
0x14001493d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014944  mov     r9d, 0A6h
0x14001494a  mov     r8d, 2
0x140014950  mov     [rsp+88h+var_68], r13
0x140014955  mov     rcx, [rcx+40h]
0x140014959  call    WPP_RECORDER_SF_
0x14001495e  xor     edx, edx; Tag
0x140014960  mov     rcx, rbp; P
0x140014963  call    cs:__imp_ExFreePoolWithTag
0x14001496a  nop     dword ptr [rax+rax+00h]
0x14001496f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140014976  jz      short loc_140014999
0x140014978  mov     rcx, cs:WPP_GLOBAL_Control
0x14001497f  mov     r9d, 0A7h
0x140014985  mov     r8d, 3
0x14001498b  mov     [rsp+88h+var_68], r13
0x140014990  mov     rcx, [rcx+40h]
0x140014994  call    WPP_RECORDER_SF_
0x140014999  add     rsp, 48h
0x14001499d  pop     r15
0x14001499f  pop     r14
0x1400149a1  pop     r13
0x1400149a3  pop     r12
0x1400149a5  pop     rdi
0x1400149a6  pop     rsi
0x1400149a7  pop     rbp
0x1400149a8  pop     rbx
0x1400149a9  retn
```
