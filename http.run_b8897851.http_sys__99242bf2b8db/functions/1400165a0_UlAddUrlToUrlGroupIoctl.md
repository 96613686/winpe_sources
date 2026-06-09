# UlAddUrlToUrlGroupIoctl

- ea: `0x1400165a0`
- end: `0x140016864`
- name: `UlAddUrlToUrlGroupIoctl`
- size: `708`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400165a0`
- `0x1400172ac`
- `0x140017370`
- `0x140018854`
- `0x140019680`
- `0x140019980`
- `0x1400265f8`
- `0x140167700`
- `0x140167b40`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!SeCreateAccessState` at `0x1400167b7`
- `ntoskrnl!SeCreateAccessState` at `0x1400167b7`
- `ntoskrnl!SeDeleteAccessState` at `0x1400167f1`
- `ntoskrnl!SeDeleteAccessState` at `0x1400167f1`
- `ntoskrnl!IoIs32bitProcess` at `0x140016691`
- `ntoskrnl!IoIs32bitProcess` at `0x140016691`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140016776`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140016776`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x140016829`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x140016829`

## pseudocode

```c
__int64 __fastcall UlAddUrlToUrlGroupIoctl(PIRP Irp, __int64 a2)
{
  int CommChannel; // ebx
  BOOLEAN v6; // si
  __int64 v7; // rdx
  int *v8; // rsi
  unsigned int v9; // edi
  int ThreadObjectCompartmentId; // ebx
  bool v11; // zf
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  _OWORD v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v17[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+90h] [rbp-70h]
  int v19[40]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v20[224]; // [rsp+140h] [rbp+40h] BYREF

  v18 = 0;
  *(_OWORD *)v17 = 0;
  memset(v19, 0, sizeof(v19));
  memset(v20, 0, sizeof(v20));
  memset(v16, 0, 28);
  *(_QWORD *)v13 = 0;
  v12 = 0;
  *(_OWORD *)v14 = 0;
  v15 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1033, 48, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, Irp, a2);
  CommChannel = UlGetCommChannel(a2, v13);
  if ( CommChannel >= 0 )
  {
    v6 = IoIs32bitProcess(Irp);
    CommChannel = UxGetInputBuffer(Irp, a2, v6 != 0 ? 48 : 64, &v12);
    if ( CommChannel >= 0 )
    {
      if ( v6 )
      {
        v7 = v12;
        v8 = v14;
        v14[0] = *(_DWORD *)v12;
        *(_QWORD *)&v14[2] = *(_QWORD *)(v12 + 8);
        *(_QWORD *)&v15 = *(_QWORD *)(v12 + 16);
        DWORD2(v15) = *(_DWORD *)(v12 + 24);
        *(_QWORD *)&v16[0] = *(unsigned int *)(v12 + 28);
        DWORD2(v16[0]) = *(_DWORD *)(v12 + 32);
        *(_QWORD *)&v16[1] = *(unsigned int *)(v12 + 36);
        DWORD2(v16[1]) = *(_DWORD *)(v12 + 40);
      }
      else
      {
        v8 = (int *)v12;
      }
      LOBYTE(v7) = Irp->RequestorMode;
      CommChannel = UxCaptureUnicodeString(v8 + 10, v7, v17);
      if ( CommChannel >= 0 )
      {
        if ( !LOWORD(v17[0]) )
        {
LABEL_14:
          CommChannel = -1073741811;
          goto LABEL_4;
        }
        v9 = 1;
        if ( *v8 == 1 )
        {
          ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
          if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v13 + 56LL) + 79LL) )
            v11 = ThreadObjectCompartmentId == 1;
          else
            v11 = ThreadObjectCompartmentId == (unsigned int)NdisGetJobObjectCompartmentId(*(_QWORD *)(*(_QWORD *)v13 + 48LL));
          if ( !v11 )
          {
            CommChannel = -1073741637;
            goto LABEL_4;
          }
        }
        else
        {
          if ( *v8 )
            goto LABEL_14;
          v9 = 2;
        }
        CommChannel = SeCreateAccessState(v19, v20, v9, &g_UrlAccessGenericMapping);
        if ( CommChannel >= 0 )
        {
          CommChannel = UlAddUrlToConfigGroup(v13[0], (int)v8, (int)v17, (int)v19, v9, Irp);
          SeDeleteAccessState(v19);
        }
      }
    }
  }
LABEL_4:
  UxFreeCapturedUnicodeString(v17);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 49, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)CommChannel);
  return UxCompleteIrpForReturn(Irp, (unsigned int)CommChannel);
}

```

## disassembly

```asm
0x1400165a0  mov     [rsp-8+arg_10], rbx
0x1400165a5  push    rbp
0x1400165a6  push    rsi
0x1400165a7  push    rdi
0x1400165a8  push    r14
0x1400165aa  push    r15
0x1400165ac  lea     rbp, [rsp-130h]
0x1400165b4  sub     rsp, 230h
0x1400165bb  mov     rax, cs:__security_cookie
0x1400165c2  xor     rax, rsp
0x1400165c5  mov     [rbp+150h+var_30], rax
0x1400165cc  mov     rdi, rdx
0x1400165cf  mov     r14, rcx
0x1400165d2  xorps   xmm0, xmm0
0x1400165d5  lea     rcx, [rbp+150h+var_1B0]; void *
0x1400165d9  xor     eax, eax
0x1400165db  xor     edx, edx; Val
0x1400165dd  mov     r8d, 0A0h; Size
0x1400165e3  mov     [rbp+150h+var_1C0], rax
0x1400165e7  movups  xmmword ptr [rbp+150h+var_1D0], xmm0
0x1400165eb  call    memset
0x1400165f0  xor     edx, edx; Val
0x1400165f2  lea     rcx, [rbp+150h+var_110]; void *
0x1400165f6  mov     r8d, 0E0h; Size
0x1400165fc  call    memset
0x140016601  xorps   xmm0, xmm0
0x140016604  xor     r15d, r15d
0x140016607  movups  [rsp+250h+var_1F0], xmm0
0x14001660c  mov     qword ptr [rsp+250h+var_218], r15
0x140016611  xor     eax, eax
0x140016613  movups  [rsp+250h+var_1F0+0Ch], xmm0
0x140016618  mov     [rsp+250h+var_220], r15
0x14001661d  movups  xmmword ptr [rsp+250h+var_210], xmm0
0x140016622  movups  [rsp+250h+var_200], xmm0
0x140016627  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14001662e  jnz     loc_140016802
0x140016634  lea     rdx, [rsp+250h+var_218]
0x140016639  mov     rcx, rdi
0x14001663c  call    UlGetCommChannel
0x140016641  mov     ebx, eax
0x140016643  test    eax, eax
0x140016645  jns     short loc_14001668E
0x140016647  lea     rcx, [rbp+150h+var_1D0]
0x14001664b  call    UxFreeCapturedUnicodeString
0x140016650  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140016657  jnz     loc_140016846
0x14001665d  mov     edx, ebx
0x14001665f  mov     rcx, r14
0x140016662  call    UxCompleteIrpForReturn
0x140016667  mov     rcx, [rbp+150h+var_30]
0x14001666e  xor     rcx, rsp; StackCookie
0x140016671  call    __security_check_cookie
0x140016676  mov     rbx, [rsp+250h+arg_10]
0x14001667e  add     rsp, 230h
0x140016685  pop     r15
0x140016687  pop     r14
0x140016689  pop     rdi
0x14001668a  pop     rsi
0x14001668b  pop     rbp
0x14001668c  retn
0x14001668e  mov     rcx, r14; Irp
0x140016691  call    cs:__imp_IoIs32bitProcess
0x140016698  nop     dword ptr [rax+rax+00h]
0x14001669d  lea     r9, [rsp+250h+var_220]
0x1400166a2  mov     rdx, rdi
0x1400166a5  mov     cl, al
0x1400166a7  mov     sil, al
0x1400166aa  neg     cl
0x1400166ac  mov     rcx, r14
0x1400166af  sbb     r8d, r8d
0x1400166b2  and     r8d, 0FFFFFFF0h
0x1400166b6  add     r8d, 40h ; '@'
0x1400166ba  call    UxGetInputBuffer
0x1400166bf  mov     ebx, eax
0x1400166c1  test    eax, eax
0x1400166c3  js      short loc_140016647
0x1400166c5  test    sil, sil
0x1400166c8  jz      loc_140016766
0x1400166ce  mov     rdx, [rsp+250h+var_220]
0x1400166d3  lea     rsi, [rsp+250h+var_210]
0x1400166d8  cmp     cs:UxKirNewUma, r15b
0x1400166df  mov     eax, [rdx]
0x1400166e1  mov     [rsp+250h+var_210], eax
0x1400166e5  mov     rax, [rdx+8]
0x1400166e9  mov     qword ptr [rsp+250h+var_210+8], rax
0x1400166ee  mov     rax, [rdx+10h]
0x1400166f2  mov     qword ptr [rsp+250h+var_200], rax
0x1400166f7  mov     eax, [rdx+18h]
0x1400166fa  mov     dword ptr [rsp+250h+var_200+8], eax
0x1400166fe  mov     eax, [rdx+1Ch]
0x140016701  mov     qword ptr [rsp+250h+var_1F0], rax
0x140016706  movzx   eax, word ptr [rdx+20h]
0x14001670a  mov     word ptr [rsp+250h+var_1F0+8], ax
0x14001670f  movzx   eax, word ptr [rdx+22h]
0x140016713  mov     word ptr [rsp+250h+var_1F0+0Ah], ax
0x140016718  mov     eax, [rdx+24h]
0x14001671b  mov     [rsp+250h+var_1E0], rax
0x140016720  mov     eax, [rdx+28h]
0x140016723  mov     [rsp+250h+var_1D8], eax
0x140016727  mov     dl, [r14+40h]
0x14001672b  lea     rcx, [rsi+28h]
0x14001672f  lea     r8, [rbp+150h+var_1D0]
0x140016733  call    UxCaptureUnicodeString
0x140016738  mov     ebx, eax
0x14001673a  test    eax, eax
0x14001673c  js      loc_140016647
0x140016742  cmp     word ptr [rbp+150h+var_1D0], r15w
0x140016747  jz      short loc_14001675C
0x140016749  mov     eax, [rsi]
0x14001674b  mov     edi, 1
0x140016750  cmp     eax, edi
0x140016752  jz      short loc_14001676D
0x140016754  test    eax, eax
0x140016756  jz      loc_14001683C
0x14001675c  mov     ebx, 0C000000Dh
0x140016761  jmp     loc_140016647
0x140016766  mov     rsi, [rsp+250h+var_220]
0x14001676b  jmp     short loc_140016727
0x14001676d  mov     rcx, gs:188h
0x140016776  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001677d  nop     dword ptr [rax+rax+00h]
0x140016782  mov     ebx, eax
0x140016784  mov     rax, qword ptr [rsp+250h+var_218]
0x140016789  mov     rcx, [rax+38h]
0x14001678d  cmp     [rcx+4Fh], r15b
0x140016791  jz      loc_140016825
0x140016797  cmp     ebx, edi
0x140016799  jz      short loc_1400167A5
0x14001679b  mov     ebx, 0C00000BBh
0x1400167a0  jmp     loc_140016647
0x1400167a5  lea     r9, g_UrlAccessGenericMapping
0x1400167ac  mov     r8d, edi
0x1400167af  lea     rdx, [rbp+150h+var_110]
0x1400167b3  lea     rcx, [rbp+150h+var_1B0]
0x1400167b7  call    cs:__imp_SeCreateAccessState
0x1400167be  nop     dword ptr [rax+rax+00h]
0x1400167c3  mov     ebx, eax
0x1400167c5  test    eax, eax
0x1400167c7  js      loc_140016647
0x1400167cd  mov     rcx, qword ptr [rsp+250h+var_218]; int
0x1400167d2  lea     r9, [rbp+150h+var_1B0]; int
0x1400167d6  mov     [rsp+250h+var_228], r14; PIRP
0x1400167db  lea     r8, [rbp+150h+var_1D0]; int
0x1400167df  mov     rdx, rsi; int
0x1400167e2  mov     [rsp+250h+var_230], edi; int
0x1400167e6  call    UlAddUrlToConfigGroup
0x1400167eb  mov     ebx, eax
0x1400167ed  lea     rcx, [rbp+150h+var_1B0]
0x1400167f1  call    cs:__imp_SeDeleteAccessState
0x1400167f8  nop     dword ptr [rax+rax+00h]
0x1400167fd  jmp     loc_140016647
0x140016802  mov     edx, 30h ; '0'
0x140016807  mov     qword ptr [rsp+250h+var_230], rdi
0x14001680c  mov     ecx, 409h
0x140016811  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x140016818  mov     r9, r14
0x14001681b  call    WPP_SF_qq
0x140016820  jmp     loc_140016634
0x140016825  mov     rcx, [rax+30h]
0x140016829  call    cs:__imp_NdisGetJobObjectCompartmentId
0x140016830  nop     dword ptr [rax+rax+00h]
0x140016835  cmp     ebx, eax
0x140016837  jmp     loc_140016799
0x14001683c  mov     edi, 2
0x140016841  jmp     loc_1400167A5
0x140016846  mov     edx, 31h ; '1'
0x14001684b  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x140016852  mov     ecx, 409h
0x140016857  mov     r9d, ebx
0x14001685a  call    WPP_SF_d
0x14001685f  jmp     loc_14001665D
```
