# ACConnect(_DEVICE_OBJECT *,CACConnectParameters const *,_FILE_OBJECT *,_EPROCESS *)

- ea: `0x14000bb00`
- end: `0x14000bf0e`
- name: `?ACConnect@@YAJPEAU_DEVICE_OBJECT@@PEBVCACConnectParameters@@PEAU_FILE_OBJECT@@PEAU_EPROCESS@@@Z`
- size: `1038`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, const struct CACConnectParameters *Address, struct _FILE_OBJECT *, struct _EPROCESS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x1400010a4`
- `0x140001c04`
- `0x140001c34`
- `0x140009008`
- `0x1400095e0`
- `0x14000bb00`
- `0x14000bf14`
- `0x14000c2a8`
- `0x14000c580`
- `0x14000f204`
- `0x14000f320`
- `0x140014270`
- `0x140024bb0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000bb5b`
- `ntoskrnl!ProbeForRead` at `0x14000bb72`
- `ntoskrnl!ProbeForRead` at `0x14000bb91`
- `ntoskrnl!ProbeForRead` at `0x14000bb5b`
- `ntoskrnl!ProbeForRead` at `0x14000bb72`
- `ntoskrnl!ProbeForRead` at `0x14000bb91`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000bc98`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000bc98`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000bcb5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000bcb5`

## pseudocode

```c
__int64 __fastcall ACConnect(
        struct _DEVICE_OBJECT *a1,
        const struct CACConnectParameters *Address,
        struct _FILE_OBJECT *a3,
        struct _EPROCESS *a4)
{
  _QWORD *DeviceExtension; // r14
  __int64 v8; // rdx
  __int64 v9; // r8
  int i; // ebx
  const wchar_t *v11; // rsi
  wchar_t *v12; // rax
  __int128 v14; // xmm6
  int v15; // esi
  int n; // ebx
  wchar_t *v17; // rcx
  int m; // ebx
  wchar_t *v19; // rcx
  int k; // ebx
  wchar_t *v21; // rcx
  int j; // ebx
  wchar_t *v23; // rcx
  struct _GUID v24; // [rsp+48h] [rbp-B0h] BYREF
  struct _EPROCESS *v25; // [rsp+58h] [rbp-A0h]
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-98h] BYREF
  wchar_t *v27[2]; // [rsp+80h] [rbp-78h]
  __int128 v28; // [rsp+90h] [rbp-68h]

  v25 = a4;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  DeviceExtension = a1->DeviceExtension;
  ProbeForRead(Address, 0x48u, 1u);
  ProbeForRead((char *)Address + 32, 0x20u, 1u);
  *(_QWORD *)&v24.Data1 = *((_QWORD *)Address + 2);
  ProbeForRead(*(volatile void **)&v24.Data1, 0x10u, 1u);
  for ( i = 0; i < 4; ++i )
  {
    v11 = (const wchar_t *)*((_QWORD *)Address + i + 4);
    if ( v11 )
    {
      ACWCUserStringLen(*((wchar_t **)Address + i + 4));
      v12 = ACpDupString(v11);
      v27[i] = v12;
      if ( !v12 )
      {
        while ( --i >= 0 )
          operator delete(v27[i]);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 13, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids);
        }
        return 3221225626LL;
      }
    }
  }
  v14 = *(_OWORD *)*(_QWORD *)&v24.Data1;
  v24 = *(struct _GUID *)*(_QWORD *)&v24.Data1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_iDi(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      v8,
      v9,
      *(_QWORD *)Address,
      *((_DWORD *)Address + 6),
      *((_QWORD *)Address + 1),
      i);
  }
  g_ulFailureInjectionPoint = *((_DWORD *)Address + 17);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  v15 = ConnectAccessCheck(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( v15 >= 0 )
  {
    ACpDestroyHeap(a1);
    g_ulHeapPoolSize = (*((_DWORD *)Address + 6) + 0xFFFF) & 0xFFFF0000;
    ACpSetSequentialID(a1, *(_QWORD *)Address);
    DeviceExtension[43] = *((_QWORD *)Address + 1);
    *((_DWORD *)DeviceExtension + 249) = *((_DWORD *)Address + 16);
    if ( ACpCreateHeap(a1, v27[0], v27[1], (const wchar_t *)v28, *((const wchar_t **)&v28 + 1)) )
    {
      if ( ACpCreateMachineQueues(a1, &v24, a3) )
      {
        DeviceExtension[10] = v25;
        DeviceExtension[11] = a3;
        *((_OWORD *)DeviceExtension + 6) = v14;
        for ( j = 0; j < 4; ++j )
        {
          v23 = v27[j];
          if ( v23 )
            operator delete(v23);
        }
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 17, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids);
        }
        for ( k = 0; k < 4; ++k )
        {
          v21 = v27[k];
          if ( v21 )
            operator delete(v21);
        }
        return 3221225626LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 16, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids);
      }
      for ( m = 0; m < 4; ++m )
      {
        v19 = v27[m];
        if ( v19 )
          operator delete(v19);
      }
      return 3221225626LL;
    }
  }
  else
  {
    for ( n = 0; n < 4; ++n )
    {
      v17 = v27[n];
      if ( v17 )
        operator delete(v17);
    }
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x14000bb00  mov     r11, rsp
0x14000bb03  push    rbx
0x14000bb04  push    rsi
0x14000bb05  push    rdi
0x14000bb06  push    r12
0x14000bb08  push    r13
0x14000bb0a  push    r14
0x14000bb0c  push    r15
0x14000bb0e  sub     rsp, 0C0h
0x14000bb15  movaps  xmmword ptr [r11-48h], xmm6
0x14000bb1a  mov     rax, cs:__security_cookie
0x14000bb21  xor     rax, rsp
0x14000bb24  mov     [rsp+0F8h+var_58], rax
0x14000bb2c  mov     [rsp+0F8h+var_A0], r9
0x14000bb31  mov     r12, r8
0x14000bb34  mov     rdi, rdx
0x14000bb37  mov     r13, rcx
0x14000bb3a  xorps   xmm0, xmm0
0x14000bb3d  movups  xmmword ptr [r11-78h], xmm0
0x14000bb42  movups  xmmword ptr [r11-68h], xmm0
0x14000bb47  mov     r14, [rcx+40h]
0x14000bb4b  mov     r15d, 1
0x14000bb51  mov     r8d, r15d; Alignment
0x14000bb54  lea     edx, [r15+47h]; Length
0x14000bb58  mov     rcx, rdi; Address
0x14000bb5b  call    cs:__imp_ProbeForRead
0x14000bb62  nop     dword ptr [rax+rax+00h]
0x14000bb67  lea     rcx, [rdi+20h]; Address
0x14000bb6b  mov     r8d, r15d; Alignment
0x14000bb6e  lea     edx, [r15+1Fh]; Length
0x14000bb72  call    cs:__imp_ProbeForRead
0x14000bb79  nop     dword ptr [rax+rax+00h]
0x14000bb7e  mov     rsi, [rdi+10h]
0x14000bb82  mov     qword ptr [rsp+0F8h+var_B0.Data1], rsi
0x14000bb87  mov     r8d, r15d; Alignment
0x14000bb8a  lea     edx, [r15+0Fh]; Length
0x14000bb8e  mov     rcx, rsi; Address
0x14000bb91  call    cs:__imp_ProbeForRead
0x14000bb98  nop     dword ptr [rax+rax+00h]
0x14000bb9d  nop
0x14000bb9e  xor     ebx, ebx
0x14000bba0  mov     [rsp+0F8h+var_C8], ebx
0x14000bba4  cmp     ebx, 4
0x14000bba7  jge     loc_14000BC3A
0x14000bbad  movsxd  r15, ebx
0x14000bbb0  mov     rsi, [rdi+r15*8+20h]
0x14000bbb5  test    rsi, rsi
0x14000bbb8  jz      short loc_14000BC2C
0x14000bbba  mov     rcx, rsi; wchar_t *
0x14000bbbd  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x14000bbc2  mov     rcx, rsi; Src
0x14000bbc5  call    ?ACpDupString@@YAPEA_WPEB_W@Z; ACpDupString(wchar_t const *)
0x14000bbca  mov     [rsp+r15*8+0F8h+var_78], rax
0x14000bbd2  test    rax, rax
0x14000bbd5  jnz     short loc_14000BC2C
0x14000bbd7  dec     ebx
0x14000bbd9  mov     [rsp+0F8h+var_C8], ebx
0x14000bbdd  test    ebx, ebx
0x14000bbdf  js      short loc_14000BBF3
0x14000bbe1  movsxd  rcx, ebx
0x14000bbe4  mov     rcx, [rsp+rcx*8+0F8h+var_78]; void *
0x14000bbec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bbf1  jmp     short loc_14000BBD7
0x14000bbf3  lea     rbx, WPP_GLOBAL_Control
0x14000bbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc01  cmp     rcx, rbx
0x14000bc04  jz      short loc_14000BC22
0x14000bc06  mov     eax, [rcx+6Ch]
0x14000bc09  test    al, 1
0x14000bc0b  jz      short loc_14000BC22
0x14000bc0d  mov     edx, 0Dh
0x14000bc12  lea     r8, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids
0x14000bc19  mov     rcx, [rcx+58h]
0x14000bc1d  call    WPP_SF_
0x14000bc22  mov     eax, 0C000009Ah
0x14000bc27  jmp     loc_14000BEE2
0x14000bc2c  mov     r15d, 1
0x14000bc32  add     ebx, r15d
0x14000bc35  jmp     loc_14000BBA0
0x14000bc3a  mov     rax, qword ptr [rsp+0F8h+var_B0.Data1]
0x14000bc3f  movups  xmm6, xmmword ptr [rax]
0x14000bc42  movups  xmmword ptr [rsp+0F8h+var_B0.Data1], xmm6
0x14000bc47  lea     rbx, WPP_GLOBAL_Control
0x14000bc4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc55  cmp     rcx, rbx
0x14000bc58  jz      short loc_14000BC7D
0x14000bc5a  mov     eax, [rcx+6Ch]
0x14000bc5d  test    al, 4
0x14000bc5f  jz      short loc_14000BC7D
0x14000bc61  mov     rax, [rdi+8]
0x14000bc65  mov     [rsp+0F8h+var_D0], rax
0x14000bc6a  mov     eax, [rdi+18h]
0x14000bc6d  mov     dword ptr [rsp+0F8h+var_D8], eax
0x14000bc71  mov     r9, [rdi]
0x14000bc74  mov     rcx, [rcx+58h]
0x14000bc78  call    WPP_SF_iDi
0x14000bc7d  mov     eax, [rdi+44h]
0x14000bc80  mov     cs:?g_ulFailureInjectionPoint@@3KA, eax; ulong g_ulFailureInjectionPoint
0x14000bc86  xorps   xmm0, xmm0
0x14000bc89  movups  xmmword ptr [rsp+0F8h+SubjectContext.ClientToken], xmm0
0x14000bc8e  movups  xmmword ptr [rsp+0F8h+SubjectContext.PrimaryToken], xmm0
0x14000bc93  lea     rcx, [rsp+0F8h+SubjectContext]; SubjectContext
0x14000bc98  call    cs:__imp_SeCaptureSubjectContext
0x14000bc9f  nop     dword ptr [rax+rax+00h]
0x14000bca4  lea     rcx, [rsp+0F8h+SubjectContext]; SubjectContext
0x14000bca9  call    ?ConnectAccessCheck@@YAJPEAU_SECURITY_SUBJECT_CONTEXT@@@Z; ConnectAccessCheck(_SECURITY_SUBJECT_CONTEXT *)
0x14000bcae  mov     esi, eax
0x14000bcb0  lea     rcx, [rsp+0F8h+SubjectContext]; SubjectContext
0x14000bcb5  call    cs:__imp_SeReleaseSubjectContext
0x14000bcbc  nop     dword ptr [rax+rax+00h]
0x14000bcc1  test    esi, esi
0x14000bcc3  jns     short loc_14000BCF1
0x14000bcc5  xor     ebx, ebx
0x14000bcc7  mov     [rsp+0F8h+var_C4], ebx
0x14000bccb  cmp     ebx, 4
0x14000bcce  jge     short loc_14000BCEA
0x14000bcd0  movsxd  rcx, ebx
0x14000bcd3  mov     rcx, [rsp+rcx*8+0F8h+var_78]; void *
0x14000bcdb  test    rcx, rcx
0x14000bcde  jz      short loc_14000BCE5
0x14000bce0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bce5  add     ebx, r15d
0x14000bce8  jmp     short loc_14000BCC7
0x14000bcea  mov     eax, esi
0x14000bcec  jmp     loc_14000BEE2
0x14000bcf1  mov     rcx, r13; struct _DEVICE_OBJECT *
0x14000bcf4  call    ?ACpDestroyHeap@@YAXPEAU_DEVICE_OBJECT@@@Z; ACpDestroyHeap(_DEVICE_OBJECT *)
0x14000bcf9  mov     eax, [rdi+18h]
0x14000bcfc  add     eax, 0FFFFh
0x14000bd01  and     eax, 0FFFF0000h
0x14000bd06  mov     cs:?g_ulHeapPoolSize@@3KA, eax; ulong g_ulHeapPoolSize
0x14000bd0c  mov     rdx, [rdi]; unsigned __int64
0x14000bd0f  mov     rcx, r13; struct _DEVICE_OBJECT *
0x14000bd12  call    ?ACpSetSequentialID@@YAXPEAU_DEVICE_OBJECT@@_K@Z; ACpSetSequentialID(_DEVICE_OBJECT *,unsigned __int64)
0x14000bd17  mov     rcx, [rdi+8]
0x14000bd1b  mov     [r14+158h], rcx
0x14000bd22  mov     eax, [rdi+40h]
0x14000bd25  mov     [r14+3E4h], eax
0x14000bd2c  mov     rax, [rsp+0F8h+var_60]
0x14000bd34  mov     [rsp+0F8h+var_D8], rax; wchar_t *
0x14000bd39  mov     r9, [rsp+0F8h+var_68]; wchar_t *
0x14000bd41  mov     r8, [rsp+0F8h+var_70]; wchar_t *
0x14000bd49  mov     rdx, [rsp+0F8h+var_78]; wchar_t *
0x14000bd51  mov     rcx, r13; struct _DEVICE_OBJECT *
0x14000bd54  call    ?ACpCreateHeap@@YAPEAXPEAU_DEVICE_OBJECT@@PEB_W111@Z; ACpCreateHeap(_DEVICE_OBJECT *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x14000bd59  test    rax, rax
0x14000bd5c  jnz     short loc_14000BDB6
0x14000bd5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd65  cmp     rcx, rbx
0x14000bd68  jz      short loc_14000BD87
0x14000bd6a  mov     eax, [rcx+6Ch]
0x14000bd6d  test    r15b, al
0x14000bd70  jz      short loc_14000BD87
0x14000bd72  mov     edx, 10h
0x14000bd77  lea     r8, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids
0x14000bd7e  mov     rcx, [rcx+58h]
0x14000bd82  call    WPP_SF_
0x14000bd87  xor     ebx, ebx
0x14000bd89  mov     [rsp+0F8h+var_C0], ebx
0x14000bd8d  cmp     ebx, 4
0x14000bd90  jge     short loc_14000BDAC
0x14000bd92  movsxd  rax, ebx
0x14000bd95  mov     rcx, [rsp+rax*8+0F8h+var_78]; void *
0x14000bd9d  test    rcx, rcx
0x14000bda0  jz      short loc_14000BDA7
0x14000bda2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bda7  add     ebx, r15d
0x14000bdaa  jmp     short loc_14000BD89
0x14000bdac  mov     eax, 0C000009Ah
0x14000bdb1  jmp     loc_14000BEE2
0x14000bdb6  mov     r8, r12; struct _FILE_OBJECT *
0x14000bdb9  lea     rdx, [rsp+0F8h+var_B0]; struct _GUID *
0x14000bdbe  mov     rcx, r13; struct _DEVICE_OBJECT *
0x14000bdc1  call    ?ACpCreateMachineQueues@@YAPEAVCQueue@@PEAU_DEVICE_OBJECT@@PEBU_GUID@@PEAU_FILE_OBJECT@@@Z; ACpCreateMachineQueues(_DEVICE_OBJECT *,_GUID const *,_FILE_OBJECT *)
0x14000bdc6  test    rax, rax
0x14000bdc9  jnz     short loc_14000BE23
0x14000bdcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdd2  cmp     rcx, rbx
0x14000bdd5  jz      short loc_14000BDF4
0x14000bdd7  mov     eax, [rcx+6Ch]
0x14000bdda  test    r15b, al
0x14000bddd  jz      short loc_14000BDF4
0x14000bddf  mov     edx, 11h
0x14000bde4  lea     r8, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids
0x14000bdeb  mov     rcx, [rcx+58h]
0x14000bdef  call    WPP_SF_
0x14000bdf4  xor     ebx, ebx
0x14000bdf6  mov     [rsp+0F8h+var_BC], ebx
0x14000bdfa  cmp     ebx, 4
0x14000bdfd  jge     short loc_14000BE19
0x14000bdff  movsxd  rax, ebx
0x14000be02  mov     rcx, [rsp+rax*8+0F8h+var_78]; void *
0x14000be0a  test    rcx, rcx
0x14000be0d  jz      short loc_14000BE14
0x14000be0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000be14  add     ebx, r15d
0x14000be17  jmp     short loc_14000BDF6
0x14000be19  mov     eax, 0C000009Ah
0x14000be1e  jmp     loc_14000BEE2
0x14000be23  mov     rax, [rsp+0F8h+var_A0]
0x14000be28  mov     [r14+50h], rax
0x14000be2c  mov     [r14+58h], r12
0x14000be30  movdqu  xmmword ptr [r14+60h], xmm6
0x14000be36  xor     ebx, ebx
0x14000be38  mov     [rsp+0F8h+var_B8], ebx
0x14000be3c  cmp     ebx, 4
0x14000be3f  jge     short loc_14000BE5B
0x14000be41  movsxd  rax, ebx
0x14000be44  mov     rcx, [rsp+rax*8+0F8h+var_78]; void *
0x14000be4c  test    rcx, rcx
0x14000be4f  jz      short loc_14000BE56
0x14000be51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000be56  add     ebx, r15d
0x14000be59  jmp     short loc_14000BE38
0x14000be5b  xor     eax, eax
0x14000be5d  jmp     loc_14000BEE2
0x14000be62  mov     edi, eax
0x14000be64  xor     ebx, ebx
0x14000be66  mov     [rsp+0F8h+var_B4], ebx
0x14000be6a  movsxd  rcx, ebx
0x14000be6d  mov     rcx, [rsp+rcx*8+0F8h+var_78]; void *
0x14000be75  test    rcx, rcx
0x14000be78  jz      short loc_14000BE7F
0x14000be7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000be7f  inc     ebx
0x14000be81  mov     [rsp+0F8h+var_B4], ebx
0x14000be85  cmp     ebx, 4
0x14000be88  jl      short loc_14000BE6A
0x14000be8a  lea     rax, WPP_GLOBAL_Control
0x14000be91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be98  cmp     rcx, rax
0x14000be9b  jz      short loc_14000BEBC
0x14000be9d  mov     eax, [rcx+6Ch]
0x14000bea0  test    al, 1
0x14000bea2  jz      short loc_14000BEBC
0x14000bea4  mov     edx, 0Eh
0x14000bea9  mov     r9d, edi
0x14000beac  lea     r8, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids
0x14000beb3  mov     rcx, [rcx+58h]
0x14000beb7  call    WPP_SF_d
0x14000bebc  mov     eax, edi
0x14000bebe  jmp     short loc_14000BEE2
0x14000bec0  mov     edi, eax
0x14000bec2  xor     ebx, ebx
0x14000bec4  movsxd  rcx, ebx
0x14000bec7  mov     rcx, [rsp+rcx*8+0F8h+var_78]; void *
0x14000becf  test    rcx, rcx
0x14000bed2  jz      short loc_14000BED9
0x14000bed4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bed9  inc     ebx
0x14000bedb  cmp     ebx, 4
0x14000bede  jl      short loc_14000BEC4
0x14000bee0  mov     eax, edi
0x14000bee2  mov     rcx, [rsp+0F8h+var_58]
0x14000beea  xor     rcx, rsp; StackCookie
0x14000beed  call    __security_check_cookie
0x14000bef2  movaps  xmm6, [rsp+0F8h+var_48]
0x14000befa  add     rsp, 0C0h
0x14000bf01  pop     r15
0x14000bf03  pop     r14
0x14000bf05  pop     r13
0x14000bf07  pop     r12
0x14000bf09  pop     rdi
0x14000bf0a  pop     rsi
0x14000bf0b  pop     rbx
0x14000bf0c  retn
```
