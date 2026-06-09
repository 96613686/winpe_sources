# NsiSetParameterEx

- ea: `0x140021d30`
- end: `0x140022070`
- name: `NsiSetParameterEx`
- size: `832`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020db0`

## callees

- `0x140021324`
- `0x140021d30`
- `0x1400223f0`
- `0x140023a40`
- `0x140023c30`
- `0x140026fac`
- `0x14004f3bc`
- `0x140050ea4`
- `0x1400512d8`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`
- `0x140078400`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14007af18`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007af18`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021dc2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021dc2`

## pseudocode

```c
__int64 __fastcall NsiSetParameterEx(__int64 a1)
{
  unsigned int v2; // r8d
  __int64 v3; // r9
  __int64 v4; // r8
  int v5; // ebx
  __int64 NmpContext; // rax
  __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // r8
  __int64 v11; // rdx
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  int v14; // eax
  int v15; // eax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  __int128 *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int128 *v24; // rdx
  char CurrentProcessId; // si
  int v26; // r9d
  __int64 (__fastcall *v27)(_QWORD *); // r10
  int v28; // eax
  __int128 v29; // xmm0
  size_t Size; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+9Ch] [rbp-64h]
  int v38; // [rsp+A0h] [rbp-60h]
  int v39; // [rsp+A4h] [rbp-5Ch]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  _OWORD v41[5]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v42; // [rsp+100h] [rbp+0h] BYREF

  memset(v41, 0, 0x48u);
  v31 = 0;
  v32 = 0;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v18 = *(_QWORD *)(a1 + 16);
    v19 = *(_DWORD *)(a1 + 32);
    v20 = *(_DWORD *)(a1 + 24);
    v42 = 0;
    v21 = (__int128 *)(v18 + 8);
    if ( !v18 )
      v21 = &v42;
    CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
    NdisGetCurrentThreadCompartmentScope(&v31, &v32);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v31,
        v2,
        (unsigned int)"NsiSetParameterEx",
        (__int64)v21,
        v20,
        v19,
        CurrentProcessId,
        0,
        v32,
        v31);
    }
  }
  v3 = *(unsigned int *)(a1 + 32);
  if ( (unsigned int)v3 > 2 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_24;
    }
    v22 = 32;
LABEL_58:
    WPP_SF_d(v17->AttachedDevice, v22, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v3);
    goto LABEL_24;
  }
  v2 = *(_DWORD *)(a1 + 36);
  if ( v2 > 7 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_24;
    }
    v22 = 33;
    v3 = v2;
    goto LABEL_58;
  }
  if ( *(_DWORD *)(a1 + 56) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
    }
    goto LABEL_24;
  }
  if ( (_DWORD)v3 )
  {
    if ( KeGetCurrentIrql() < 2u )
    {
      LOBYTE(v4) = *(_DWORD *)(a1 + 36) == 4;
      v5 = NsipAccessCheck(a1 + 8, 0, v4);
      if ( v5 < 0 )
        goto LABEL_17;
    }
    NmpContext = NsipGetNmpContext(a1 + 8);
    v7 = NmpContext;
    if ( !NmpContext )
    {
      v5 = -1073741637;
      goto LABEL_17;
    }
    v8 = *(_QWORD *)(NmpContext + 48);
    v9 = *(unsigned int *)(a1 + 24);
    v5 = NsipValidateSetParameterRequest(v8, a1);
    if ( v5 < 0 )
      goto LABEL_16;
    v10 = *(_QWORD *)(v8 + 8);
    v11 = 104 * v9;
    if ( *(_QWORD *)(104 * v9 + v10 + 40) )
    {
      v12 = *(_OWORD *)(a1 + 40);
      v13 = *(_OWORD *)(a1 + 56);
      *((_QWORD *)&v41[3] + 1) = *(unsigned int *)(a1 + 36);
      v41[1] = v12;
      *(_QWORD *)&v41[3] = *(_QWORD *)(a1 + 72);
      v41[2] = v13;
      *(_QWORD *)&v41[4] = 0;
      *(_QWORD *)&v41[0] = *(_QWORD *)(v7 + 40);
      *((_QWORD *)&v41[0] + 1) = *(_QWORD *)(v11 + v10 + 24);
      v14 = (*(__int64 (__fastcall **)(_OWORD *))(v11 + v10 + 40))(v41);
    }
    else
    {
      v37 = 0;
      v34 = 0;
      if ( *(_DWORD *)(a1 + 76)
        || (v26 = *(_DWORD *)(a1 + 72), v26 != *(_DWORD *)(v11 + v10 + 4))
        || (v27 = *(__int64 (__fastcall **)(_QWORD *))(v11 + v10 + 56)) == 0 )
      {
        v5 = -1073741811;
        goto LABEL_16;
      }
      v28 = *(_DWORD *)(a1 + 36);
      v29 = *(_OWORD *)(a1 + 40);
      v35 = *(_QWORD *)(a1 + 64);
      v33[0] = *(_QWORD *)(v7 + 40);
      v33[1] = *(_QWORD *)(v11 + v10 + 24);
      v38 = v28;
      v34 = v29;
      v36 = v26;
      v39 = 0;
      v40 = 0;
      v14 = v27(v33);
    }
    v5 = v14;
  }
  else
  {
    v7 = 0;
    v5 = 0;
  }
  v15 = *(_DWORD *)(a1 + 32);
  if ( !v15 || v15 == 2 && v5 >= 0 )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
LABEL_20:
      LODWORD(Size) = *(_DWORD *)(a1 + 72);
      v5 = NsipWritePersistentData(
             (int)a1 + 8,
             *(_DWORD *)(a1 + 36),
             (int)a1 + 40,
             *(_QWORD *)(a1 + 64),
             0,
             Size,
             *(_DWORD *)(a1 + 76),
             0);
      goto LABEL_15;
    }
    if ( v7 || (v7 = NsipGetNmpContext(a1 + 8)) != 0 )
    {
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(v7 + 24);
      goto LABEL_20;
    }
LABEL_24:
    v5 = -1073741811;
    goto LABEL_17;
  }
LABEL_15:
  if ( v7 )
LABEL_16:
    NsipDereferenceNmpContext(v7);
LABEL_17:
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v23 = *(_QWORD *)(a1 + 16);
    v42 = 0;
    v24 = (__int128 *)(v23 + 8);
    if ( !v23 )
      v24 = &v42;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_s_guid_dddqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v24,
        v2,
        (unsigned int)"NsiSetParameterEx",
        (__int64)v24,
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        0,
        0,
        0,
        0,
        v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140021d30  mov     [rsp-8+arg_8], rbx
0x140021d35  mov     [rsp-8+arg_10], rsi
0x140021d3a  push    rbp
0x140021d3b  push    rdi
0x140021d3c  push    r12
0x140021d3e  push    r14
0x140021d40  push    r15
0x140021d42  lea     rbp, [rsp-20h]
0x140021d47  sub     rsp, 120h
0x140021d4e  mov     rax, cs:__security_cookie
0x140021d55  xor     rax, rsp
0x140021d58  mov     [rbp+40h+var_30], rax
0x140021d5c  xor     edx, edx; Val
0x140021d5e  mov     rdi, rcx
0x140021d61  lea     rcx, [rbp+40h+var_90]; void *
0x140021d65  lea     r8d, [rdx+48h]; Size
0x140021d69  call    memset
0x140021d6e  mov     rax, cs:WPP_GLOBAL_Control
0x140021d75  lea     rdx, WPP_GLOBAL_Control
0x140021d7c  xor     r12d, r12d
0x140021d7f  mov     [rsp+140h+var_E0], r12d
0x140021d84  mov     [rsp+140h+var_D8], r12d
0x140021d89  cmp     byte ptr [rax+29h], 5
0x140021d8d  jnb     loc_140021F4A
0x140021d93  mov     r9d, [rdi+20h]
0x140021d97  cmp     r9d, 2
0x140021d9b  ja      loc_140021F30
0x140021da1  mov     r8d, [rdi+24h]
0x140021da5  cmp     r8d, 7
0x140021da9  ja      loc_140021FF3
0x140021daf  cmp     [rdi+38h], r12d
0x140021db3  jnz     loc_140021F7E
0x140021db9  test    r9d, r9d
0x140021dbc  jz      loc_140021FB8
0x140021dc2  call    cs:__imp_KeGetCurrentIrql
0x140021dc9  nop     dword ptr [rax+rax+00h]
0x140021dce  cmp     al, 2
0x140021dd0  jnb     short loc_140021DEF
0x140021dd2  cmp     dword ptr [rdi+24h], 4
0x140021dd6  lea     rcx, [rdi+8]
0x140021dda  setz    r8b
0x140021dde  xor     edx, edx
0x140021de0  call    NsipAccessCheck
0x140021de5  mov     ebx, eax
0x140021de7  test    eax, eax
0x140021de9  js      loc_140021E97
0x140021def  lea     rcx, [rdi+8]
0x140021df3  call    NsipGetNmpContext
0x140021df8  mov     rsi, rax
0x140021dfb  test    rax, rax
0x140021dfe  jz      loc_140021FAE
0x140021e04  mov     r14, [rax+30h]
0x140021e08  mov     rdx, rdi
0x140021e0b  mov     r15d, [rdi+18h]
0x140021e0f  mov     rcx, r14
0x140021e12  call    NsipValidateSetParameterRequest
0x140021e17  mov     ebx, eax
0x140021e19  test    eax, eax
0x140021e1b  js      short loc_140021E8F
0x140021e1d  mov     r8, [r14+8]
0x140021e21  imul    rdx, r15, 68h ; 'h'
0x140021e25  cmp     [rdx+r8+28h], r12
0x140021e2a  jz      loc_140021F10
0x140021e30  movups  xmm0, xmmword ptr [rdi+28h]
0x140021e34  mov     eax, [rdi+24h]
0x140021e37  lea     rcx, [rbp+40h+var_90]
0x140021e3b  movups  xmm1, xmmword ptr [rdi+38h]
0x140021e3f  mov     [rbp+40h+var_58], eax
0x140021e42  movdqu  [rbp+40h+var_80], xmm0
0x140021e47  mov     [rbp+40h+var_54], r12d
0x140021e4b  movsd   xmm0, qword ptr [rdi+48h]
0x140021e50  movsd   [rbp+40h+var_60], xmm0
0x140021e55  movaps  [rbp+40h+var_70], xmm1
0x140021e59  mov     [rbp+40h+var_50], r12
0x140021e5d  mov     rax, [rsi+28h]
0x140021e61  mov     [rbp+40h+var_90], rax
0x140021e65  mov     rax, [rdx+r8+18h]
0x140021e6a  mov     [rbp+40h+var_88], rax
0x140021e6e  mov     rax, [rdx+r8+28h]
0x140021e73  call    _guard_dispatch_icall
0x140021e78  mov     ebx, eax
0x140021e7a  mov     eax, [rdi+20h]
0x140021e7d  test    eax, eax
0x140021e7f  jz      short loc_140021ED3
0x140021e81  cmp     eax, 2
0x140021e84  jz      loc_140021FC3
0x140021e8a  test    rsi, rsi
0x140021e8d  jz      short loc_140021E97
0x140021e8f  mov     rcx, rsi
0x140021e92  call    NsipDereferenceNmpContext
0x140021e97  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e9e  cmp     byte ptr [rcx+29h], 5
0x140021ea2  jnb     loc_140022044
0x140021ea8  mov     eax, ebx
0x140021eaa  mov     rcx, [rbp+40h+var_30]
0x140021eae  xor     rcx, rsp; StackCookie
0x140021eb1  call    __security_check_cookie
0x140021eb6  lea     r11, [rsp+140h+var_20]
0x140021ebe  mov     rbx, [r11+38h]
0x140021ec2  mov     rsi, [r11+40h]
0x140021ec6  mov     rsp, r11
0x140021ec9  pop     r15
0x140021ecb  pop     r14
0x140021ecd  pop     r12
0x140021ecf  pop     rdi
0x140021ed0  pop     rbp
0x140021ed1  retn
0x140021ed3  cmp     [rdi+10h], r12
0x140021ed7  jz      loc_140021FD0
0x140021edd  mov     eax, [rdi+4Ch]
0x140021ee0  lea     r8, [rdi+28h]; int
0x140021ee4  mov     r9, [rdi+40h]; int
0x140021ee8  lea     rcx, [rdi+8]; int
0x140021eec  mov     edx, [rdi+24h]; int
0x140021eef  mov     [rsp+140h+var_108], r12b; char
0x140021ef4  mov     [rsp+140h+var_110], eax; int
0x140021ef8  mov     eax, [rdi+48h]
0x140021efb  mov     dword ptr [rsp+140h+Size], eax; Size
0x140021eff  mov     [rsp+140h+var_120], r12; void *
0x140021f04  call    NsipWritePersistentData
0x140021f09  mov     ebx, eax
0x140021f0b  jmp     loc_140021E8A
0x140021f10  xorps   xmm0, xmm0
0x140021f13  mov     [rbp+40h+var_A4], r12d
0x140021f17  movdqa  [rbp+40h+var_C0], xmm0
0x140021f1c  cmp     [rdi+4Ch], r12d
0x140021f20  jz      loc_14007AFA9
0x140021f26  mov     ebx, 0C000000Dh
0x140021f2b  jmp     loc_140021E8F
0x140021f30  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f37  cmp     rcx, rdx
0x140021f3a  jnz     loc_140022025
0x140021f40  mov     ebx, 0C000000Dh
0x140021f45  jmp     loc_140021E97
0x140021f4a  mov     eax, [rax+2Ch]
0x140021f4d  test    al, 10h
0x140021f4f  jz      loc_140021D93
0x140021f55  mov     rax, [rdi+10h]
0x140021f59  xorps   xmm0, xmm0
0x140021f5c  mov     r14d, [rdi+20h]
0x140021f60  mov     r15d, [rdi+18h]
0x140021f64  movups  [rbp+40h+var_40], xmm0
0x140021f68  lea     rbx, [rax+8]
0x140021f6c  test    rax, rax
0x140021f6f  jnz     loc_14007AF18
0x140021f75  lea     rbx, [rbp+40h+var_40]
0x140021f79  jmp     loc_14007AF18
0x140021f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f85  cmp     rcx, rdx
0x140021f88  jz      short loc_140021F40
0x140021f8a  cmp     byte ptr [rcx+29h], 2
0x140021f8e  jb      short loc_140021F40
0x140021f90  mov     eax, [rcx+2Ch]
0x140021f93  test    al, 10h
0x140021f95  jz      short loc_140021F40
0x140021f97  mov     rcx, [rcx+18h]
0x140021f9b  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140021fa2  mov     edx, 22h ; '"'
0x140021fa7  call    WPP_SF_
0x140021fac  jmp     short loc_140021F40
0x140021fae  mov     ebx, 0C00000BBh
0x140021fb3  jmp     loc_140021E97
0x140021fb8  mov     rsi, r12
0x140021fbb  mov     ebx, r12d
0x140021fbe  jmp     loc_140021E7A
0x140021fc3  test    ebx, ebx
0x140021fc5  js      loc_140021E8A
0x140021fcb  jmp     loc_140021ED3
0x140021fd0  test    rsi, rsi
0x140021fd3  jnz     loc_14007B009
0x140021fd9  lea     rcx, [rdi+8]
0x140021fdd  call    NsipGetNmpContext
0x140021fe2  mov     rsi, rax
0x140021fe5  test    rax, rax
0x140021fe8  jz      loc_140021F40
0x140021fee  jmp     loc_14007B009
0x140021ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ffa  cmp     rcx, rdx
0x140021ffd  jz      loc_140021F40
0x140022003  cmp     byte ptr [rcx+29h], 2
0x140022007  jb      loc_140021F40
0x14002200d  mov     eax, [rcx+2Ch]
0x140022010  test    al, 10h
0x140022012  jz      loc_140021F40
0x140022018  mov     edx, 21h ; '!'
0x14002201d  mov     r9d, r8d
0x140022020  jmp     loc_14007B016
0x140022025  cmp     byte ptr [rcx+29h], 2
0x140022029  jb      loc_140021F40
0x14002202f  mov     eax, [rcx+2Ch]
0x140022032  test    al, 10h
0x140022034  jz      loc_140021F40
0x14002203a  mov     edx, 20h ; ' '
0x14002203f  jmp     loc_14007B016
0x140022044  mov     eax, [rcx+2Ch]
0x140022047  test    al, 10h
0x140022049  jz      loc_140021EA8
0x14002204f  mov     rax, [rdi+10h]
0x140022053  xorps   xmm0, xmm0
0x140022056  movups  [rbp+40h+var_40], xmm0
0x14002205a  lea     rdx, [rax+8]
0x14002205e  test    rax, rax
0x140022061  jnz     loc_14007B02C
0x140022067  lea     rdx, [rbp+40h+var_40]
0x14002206b  jmp     loc_14007B02C
0x14007af18  call    cs:__imp_PsGetCurrentProcessId
0x14007af1f  nop     dword ptr [rax+rax+00h]
0x14007af24  mov     edx, [rsp+140h+var_E0]
0x14007af28  mov     rsi, rax
0x14007af2b  test    edx, edx
0x14007af2d  jnz     short loc_14007AF49
0x14007af2f  cmp     [rsp+140h+var_D8], r12d
0x14007af34  jnz     short loc_14007AF49
0x14007af36  lea     rdx, [rsp+140h+var_D8]
0x14007af3b  lea     rcx, [rsp+140h+var_E0]
0x14007af40  call    NdisGetCurrentThreadCompartmentScope
0x14007af45  mov     edx, [rsp+140h+var_E0]
0x14007af49  mov     rcx, cs:WPP_GLOBAL_Control
0x14007af50  lea     rax, WPP_GLOBAL_Control
0x14007af57  cmp     rcx, rax
0x14007af5a  jz      short loc_14007AF9D
0x14007af5c  cmp     byte ptr [rcx+29h], 5
0x14007af60  jb      short loc_14007AF9D
0x14007af62  mov     eax, [rcx+2Ch]
0x14007af65  test    al, 10h
0x14007af67  jz      short loc_14007AF9D
0x14007af69  mov     eax, [rsp+140h+var_D8]
0x14007af6d  lea     r9, aNsisetparamete; "NsiSetParameterEx"
0x14007af74  mov     rcx, [rcx+18h]
0x14007af78  mov     [rsp+140h+var_F0], edx
0x14007af7c  mov     [rsp+140h+var_F8], eax
0x14007af80  mov     [rsp+140h+var_100], r12
0x14007af85  mov     dword ptr [rsp+140h+var_108], esi
0x14007af89  mov     [rsp+140h+var_110], r14d
0x14007af8e  mov     dword ptr [rsp+140h+Size], r15d
0x14007af93  mov     [rsp+140h+var_120], rbx
0x14007af98  call    WPP_SF_s_guid_dddqdd
0x14007af9d  lea     rdx, WPP_GLOBAL_Control
0x14007afa4  jmp     loc_140021D93
0x14007afa9  mov     r9d, [rdi+48h]
0x14007afad  cmp     r9d, [rdx+r8+4]
0x14007afb2  jnz     loc_140021F26
0x14007afb8  mov     r10, [rdx+r8+38h]
0x14007afbd  test    r10, r10
0x14007afc0  jz      loc_140021F26
0x14007afc6  mov     rcx, [rdi+40h]
0x14007afca  mov     eax, [rdi+24h]
0x14007afcd  movups  xmm0, xmmword ptr [rdi+28h]
0x14007afd1  mov     [rbp+40h+var_B0], rcx
0x14007afd5  mov     rcx, [rsi+28h]
0x14007afd9  mov     [rsp+140h+var_D0], rcx
0x14007afde  mov     rcx, [rdx+r8+18h]
0x14007afe3  mov     [rsp+140h+var_C8], rcx
0x14007afe8  lea     rcx, [rsp+140h+var_D0]
0x14007afed  mov     [rbp+40h+var_A0], eax
0x14007aff0  mov     rax, r10
0x14007aff3  movdqu  [rbp+40h+var_C0], xmm0
0x14007aff8  mov     [rbp+40h+var_A8], r9d
0x14007affc  mov     [rbp+40h+var_9C], r12d
0x14007b000  mov     [rbp+40h+var_98], r12
0x14007b004  jmp     loc_140021E73
0x14007b009  mov     rax, [rsi+18h]
0x14007b00d  mov     [rdi+10h], rax
0x14007b011  jmp     loc_140021EDD
0x14007b016  mov     rcx, [rcx+18h]
0x14007b01a  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x14007b021  call    WPP_SF_d
0x14007b026  nop
0x14007b027  jmp     loc_140021F40
0x14007b02c  lea     rax, WPP_GLOBAL_Control
0x14007b033  cmp     rcx, rax
0x14007b036  jz      loc_140021EA8
0x14007b03c  mov     eax, [rdi+20h]
0x14007b03f  lea     r9, aNsisetparamete; "NsiSetParameterEx"
0x14007b046  mov     rcx, [rcx+18h]
0x14007b04a  mov     [rsp+140h+var_E8], ebx
0x14007b04e  mov     [rsp+140h+var_F0], r12d
0x14007b053  mov     [rsp+140h+var_F8], r12d
0x14007b058  mov     [rsp+140h+var_100], r12
0x14007b05d  mov     dword ptr [rsp+140h+var_108], r12d
0x14007b062  mov     [rsp+140h+var_110], eax
0x14007b066  mov     eax, [rdi+18h]
0x14007b069  mov     dword ptr [rsp+140h+Size], eax
0x14007b06d  mov     [rsp+140h+var_120], rdx
0x14007b072  call    WPP_SF_s_guid_dddqddD
0x14007b077  nop
0x14007b078  jmp     loc_140021EA8
```
