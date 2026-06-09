# CorBindToRuntimeHostInternal

- ea: `0x18002ca2c`
- end: `0x18002cd43`
- name: `CorBindToRuntimeHostInternal`
- size: `791`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006a00`
- `0x1800081b0`
- `0x180008c60`
- `0x18002c358`

## callees

- `0x180003740`
- `0x180008710`
- `0x18000883c`
- `0x180008bcc`
- `0x180028c88`
- `0x180029b38`
- `0x180029b70`
- `0x18002ba30`
- `0x18002ca2c`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002cc8d`
- `KERNEL32!GetProcAddress` at `0x18002ccaf`
- `KERNEL32!GetProcAddress` at `0x18002cc8d`
- `KERNEL32!GetProcAddress` at `0x18002ccaf`
- `KERNEL32!GetLastError` at `0x18002cc98`
- `KERNEL32!GetLastError` at `0x18002cc98`

## string_xrefs

- `0x18002cca8`: `DllGetClassObject`
- `0x18002cc86`: `DllGetClassObjectInternal`

## pseudocode

```c
__int64 __fastcall CorBindToRuntimeHostInternal(
        CLRFullPath *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int v13; // r13d
  unsigned __int16 *FullPath; // rax
  const struct NoThrow *v15; // rdx
  const unsigned __int16 *v16; // r8
  unsigned int v17; // esi
  RuntimeRequest *v19; // rcx
  HMODULE v20; // rbx
  int v21; // r14d
  int v22; // eax
  RuntimeRequest *v23; // rcx
  RuntimeRequest *v24; // rcx
  int Installation; // ebx
  RuntimeRequest *v26; // rcx
  RuntimeRequest *v27; // rcx
  CLRFullPath *v28; // rcx
  FARPROC ProcAddress; // rax
  HMODULE hModule; // [rsp+30h] [rbp-A1h] BYREF
  int v31; // [rsp+38h] [rbp-99h]
  __int128 v32; // [rsp+40h] [rbp-91h] BYREF
  unsigned __int16 *v33[2]; // [rsp+50h] [rbp-81h] BYREF
  __int128 v34; // [rsp+60h] [rbp-71h] BYREF
  __int128 v35; // [rsp+70h] [rbp-61h]
  __int64 v36; // [rsp+80h] [rbp-51h]
  int v37; // [rsp+88h] [rbp-49h]
  unsigned __int16 *v38; // [rsp+90h] [rbp-41h] BYREF
  int v39; // [rsp+98h] [rbp-39h]
  __int64 v40; // [rsp+A0h] [rbp-31h]
  __int64 v41; // [rsp+A8h] [rbp-29h]
  __int64 v42; // [rsp+B0h] [rbp-21h]
  int v43; // [rsp+B8h] [rbp-19h]
  __int64 v44; // [rsp+C0h] [rbp-11h]

  v13 = (int)a1;
  FullPath = CLRFullPath::GetFullPath(a1);
  v17 = a7;
  if ( FullPath || (a7 & 0x100) == 0 )
  {
    v37 = 0;
    v36 = 1;
    v32 = 0;
    *(_OWORD *)v33 = 0;
    v34 = 0;
    v35 = 0;
    v38 = 0;
    v39 = 1;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = -1;
    Installation = RuntimeRequest::CopyString(0, (const unsigned __int16 **)&v34 + 1, v16, 1);
    if ( Installation < 0 )
      goto LABEL_32;
    Installation = VerifyVersionInput(&v32, a2);
    if ( Installation < 0 )
      goto LABEL_32;
    DWORD2(v35) = v13;
    Installation = RuntimeRequest::CopyString(v26, (const unsigned __int16 **)&v38, a4, 1);
    if ( Installation < 0 )
      goto LABEL_32;
    Installation = RuntimeRequest::CopyString(v27, (const unsigned __int16 **)&v33[1], a5, 1);
    if ( Installation < 0 )
      goto LABEL_32;
    v39 = v17;
    a6 = 0;
    LODWORD(v35) = (v17 >> 4) & 1;
    if ( CLRFullPath::GetFullPath(v28)
      || (Installation = RuntimeRequest::RequestRuntimeDll((RuntimeRequest *)&v32, 1, &a6), Installation >= 0) )
    {
      hModule = 0;
      Installation = GetInstallation((CLRFullPath *)1, &hModule, 0);
      if ( Installation >= 0 )
      {
        ProcAddress = GetProcAddress(hModule, "DllGetClassObjectInternal");
        if ( !ProcAddress
          && (GetLastError() != 127 || (ProcAddress = GetProcAddress(hModule, "DllGetClassObject")) == 0) )
        {
          Installation = -2146232575;
LABEL_32:
          RuntimeRequest::~RuntimeRequest((RuntimeRequest *)&v32);
          return (unsigned int)Installation;
        }
        hModule = 0;
        Installation = ((__int64 (__fastcall *)(__int64, GUID *, HMODULE *))ProcAddress)(
                         a8,
                         &IID_IClassFactory,
                         &hModule);
        if ( Installation >= 0 )
        {
          Installation = (*(__int64 (__fastcall **)(HMODULE, _QWORD, __int64, __int64))(*(_QWORD *)hModule + 24LL))(
                           hModule,
                           0,
                           a9,
                           a10);
          (*(void (__fastcall **)(HMODULE))(*(_QWORD *)hModule + 16LL))(hModule);
        }
      }
    }
    if ( !Installation )
      Installation = a6 == 0;
    goto LABEL_32;
  }
  if ( g_PreferredVersion )
    return 2147942487LL;
  v20 = (HMODULE)operator new(0x88u, v15);
  if ( v20 )
  {
    *(_QWORD *)v20 = 0;
    *((_QWORD *)v20 + 1) = 0;
    *((_QWORD *)v20 + 2) = 0;
    *((_QWORD *)v20 + 3) = 0;
    *((_QWORD *)v20 + 4) = 0;
    *((_QWORD *)v20 + 5) = 0;
    *((_QWORD *)v20 + 6) = 0;
    *((_QWORD *)v20 + 7) = 0;
    *((_QWORD *)v20 + 8) = 1;
    *((_DWORD *)v20 + 18) = 0;
    *((_QWORD *)v20 + 10) = 0;
    *((_DWORD *)v20 + 22) = 1;
    *((_QWORD *)v20 + 12) = 0;
    *((_QWORD *)v20 + 13) = 0;
    *((_QWORD *)v20 + 14) = 0;
    *((_DWORD *)v20 + 30) = 0;
    *((_QWORD *)v20 + 16) = -1;
  }
  else
  {
    v20 = 0;
  }
  hModule = v20;
  v31 = 0;
  if ( v20 )
  {
    v31 = 1;
    v21 = RuntimeRequest::CopyString(v19, (const unsigned __int16 **)v20 + 5, a3, 1);
    if ( v21 >= 0 )
    {
      v22 = VerifyVersionInput(v20, a2);
      if ( v22 < 0
        || (*((_DWORD *)v20 + 14) = v13,
            v22 = RuntimeRequest::CopyString(v23, (const unsigned __int16 **)v20 + 10, a4, 1),
            v22 < 0) )
      {
        v21 = v22;
      }
      else
      {
        v21 = RuntimeRequest::CopyString(v24, (const unsigned __int16 **)v20 + 3, a5, 1);
        if ( v21 >= 0 )
        {
          *((_DWORD *)v20 + 22) = v17;
          v31 = 0;
          *((_DWORD *)v20 + 12) = (v17 >> 4) & 1;
          _InterlockedExchange64((volatile __int64 *)&g_PreferredVersion, (__int64)v20);
        }
      }
    }
  }
  else
  {
    v21 = -2147024882;
  }
  Wrapper<RuntimeRequest *,&void DoNothing<RuntimeRequest *>(RuntimeRequest *),&void Delete<RuntimeRequest>(RuntimeRequest *),0,&int CompareDefault<RuntimeRequest *>(RuntimeRequest *,RuntimeRequest *),2>::~Wrapper<RuntimeRequest *,&void DoNothing<RuntimeRequest *>(RuntimeRequest *),&void Delete<RuntimeRequest>(RuntimeRequest *),0,&int CompareDefault<RuntimeRequest *>(RuntimeRequest *,RuntimeRequest *),2>(&hModule);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18002ca2c  push    rbp
0x18002ca2e  push    rbx
0x18002ca2f  push    rsi
0x18002ca30  push    rdi
0x18002ca31  push    r12
0x18002ca33  push    r13
0x18002ca35  push    r14
0x18002ca37  push    r15
0x18002ca39  lea     rbp, [rsp-7]
0x18002ca3e  sub     rsp, 0D8h
0x18002ca45  mov     r12, r9
0x18002ca48  mov     r14, r8
0x18002ca4b  mov     r15, rdx
0x18002ca4e  mov     r13d, ecx
0x18002ca51  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18002ca56  mov     esi, [rbp+3Fh+arg_30]
0x18002ca59  xor     ecx, ecx; this
0x18002ca5b  test    rax, rax
0x18002ca5e  jnz     loc_18002CB84
0x18002ca64  bt      esi, 8
0x18002ca68  jnb     loc_18002CB84
0x18002ca6e  cmp     cs:?g_PreferredVersion@@3PEAVRuntimeRequest@@EA, rcx; RuntimeRequest * g_PreferredVersion
0x18002ca75  jz      short loc_18002CA81
0x18002ca77  mov     eax, 80070057h
0x18002ca7c  jmp     loc_18002CD2F
0x18002ca81  mov     ecx, 88h; unsigned __int64
0x18002ca86  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002ca8b  mov     rbx, rax
0x18002ca8e  mov     edi, 1
0x18002ca93  xor     eax, eax
0x18002ca95  test    rbx, rbx
0x18002ca98  jz      short loc_18002CAE3
0x18002ca9a  mov     [rbx], rax
0x18002ca9d  mov     [rbx+8], rax
0x18002caa1  mov     [rbx+10h], rax
0x18002caa5  mov     [rbx+18h], rax
0x18002caa9  mov     [rbx+20h], rax
0x18002caad  mov     [rbx+28h], rax
0x18002cab1  mov     [rbx+30h], rax
0x18002cab5  mov     [rbx+38h], rax
0x18002cab9  mov     [rbx+40h], rdi
0x18002cabd  mov     [rbx+48h], eax
0x18002cac0  mov     [rbx+50h], rax
0x18002cac4  mov     [rbx+58h], edi
0x18002cac7  mov     [rbx+60h], rax
0x18002cacb  mov     [rbx+68h], rax
0x18002cacf  mov     [rbx+70h], rax
0x18002cad3  mov     [rbx+78h], eax
0x18002cad6  mov     qword ptr [rbx+80h], 0FFFFFFFFFFFFFFFFh
0x18002cae1  jmp     short loc_18002CAE6
0x18002cae3  mov     rbx, rax
0x18002cae6  mov     [rsp+110h+hModule], rbx
0x18002caeb  mov     [rsp+110h+var_D8], eax
0x18002caef  test    rbx, rbx
0x18002caf2  jz      short loc_18002CB6C
0x18002caf4  lea     rdx, [rbx+28h]; unsigned __int16 **
0x18002caf8  mov     [rsp+110h+var_D8], edi
0x18002cafc  mov     r9d, edi; int
0x18002caff  mov     r8, r14; unsigned __int16 *
0x18002cb02  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002cb07  mov     r14d, eax
0x18002cb0a  test    eax, eax
0x18002cb0c  js      short loc_18002CB72
0x18002cb0e  mov     rdx, r15
0x18002cb11  mov     rcx, rbx
0x18002cb14  call    VerifyVersionInput
0x18002cb19  test    eax, eax
0x18002cb1b  jns     short loc_18002CB22
0x18002cb1d  mov     r14d, eax
0x18002cb20  jmp     short loc_18002CB72
0x18002cb22  lea     rdx, [rbx+50h]; unsigned __int16 **
0x18002cb26  mov     [rbx+38h], r13d
0x18002cb2a  mov     r9d, edi; int
0x18002cb2d  mov     r8, r12; unsigned __int16 *
0x18002cb30  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002cb35  test    eax, eax
0x18002cb37  js      short loc_18002CB1D
0x18002cb39  mov     r8, [rbp+3Fh+arg_20]; unsigned __int16 *
0x18002cb3d  lea     rdx, [rbx+18h]; unsigned __int16 **
0x18002cb41  mov     r9d, edi; int
0x18002cb44  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002cb49  mov     r14d, eax
0x18002cb4c  test    eax, eax
0x18002cb4e  js      short loc_18002CB72
0x18002cb50  mov     [rbx+58h], esi
0x18002cb53  shr     esi, 4
0x18002cb56  and     esi, edi
0x18002cb58  mov     [rsp+110h+var_D8], 0
0x18002cb60  mov     [rbx+30h], esi
0x18002cb63  xchg    rbx, cs:?g_PreferredVersion@@3PEAVRuntimeRequest@@EA; RuntimeRequest * g_PreferredVersion
0x18002cb6a  jmp     short loc_18002CB72
0x18002cb6c  mov     r14d, 8007000Eh
0x18002cb72  lea     rcx, [rsp+110h+hModule]
0x18002cb77  call    ??1?$Wrapper@PEAVRuntimeRequest@@$1??$DoNothing@PEAVRuntimeRequest@@@@YAXPEAV1@@Z$1??$Delete@VRuntimeRequest@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVRuntimeRequest@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<RuntimeRequest *,&DoNothing<RuntimeRequest *>(RuntimeRequest *),&Delete<RuntimeRequest>(RuntimeRequest *),0,&CompareDefault<RuntimeRequest *>(RuntimeRequest *,RuntimeRequest *),2>::~Wrapper<RuntimeRequest *,&DoNothing<RuntimeRequest *>(RuntimeRequest *),&Delete<RuntimeRequest>(RuntimeRequest *),0,&CompareDefault<RuntimeRequest *>(RuntimeRequest *,RuntimeRequest *),2>(void)
0x18002cb7c  mov     eax, r14d
0x18002cb7f  jmp     loc_18002CD2F
0x18002cb84  mov     edi, 1
0x18002cb89  mov     [rbp+3Fh+var_88], ecx
0x18002cb8c  xorps   xmm0, xmm0
0x18002cb8f  mov     [rbp+3Fh+var_90], rdi
0x18002cb93  xorps   xmm1, xmm1
0x18002cb96  movdqa  [rsp+110h+var_D0], xmm0
0x18002cb9c  mov     r9d, edi; int
0x18002cb9f  movdqa  xmmword ptr [rsp+110h+var_C0], xmm1
0x18002cba5  lea     rdx, [rbp+3Fh+var_A8]; unsigned __int16 **
0x18002cba9  movdqa  xmmword ptr [rbp-71h], xmm0
0x18002cbae  movups  [rbp+3Fh+var_A0], xmm1
0x18002cbb2  mov     [rbp+3Fh+var_80], rcx
0x18002cbb6  mov     [rbp+3Fh+var_78], edi
0x18002cbb9  mov     [rbp+3Fh+var_70], rcx
0x18002cbbd  mov     [rbp+3Fh+var_68], rcx
0x18002cbc1  mov     [rbp+3Fh+var_60], rcx
0x18002cbc5  mov     [rbp+3Fh+var_58], ecx
0x18002cbc8  mov     [rbp+3Fh+var_50], 0FFFFFFFFFFFFFFFFh
0x18002cbd0  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002cbd5  xor     r14d, r14d
0x18002cbd8  lea     rcx, [rsp+110h+var_D0]
0x18002cbdd  mov     ebx, eax
0x18002cbdf  test    eax, eax
0x18002cbe1  js      loc_18002CD28
0x18002cbe7  mov     rdx, r15
0x18002cbea  call    VerifyVersionInput
0x18002cbef  mov     ebx, eax
0x18002cbf1  test    eax, eax
0x18002cbf3  js      loc_18002CD23
0x18002cbf9  mov     r9d, edi; int
0x18002cbfc  mov     dword ptr [rbp+3Fh+var_A0+8], r13d
0x18002cc00  mov     r8, r12; unsigned __int16 *
0x18002cc03  lea     rdx, [rbp+3Fh+var_80]; unsigned __int16 **
0x18002cc07  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002cc0c  mov     ebx, eax
0x18002cc0e  test    eax, eax
0x18002cc10  js      loc_18002CD23
0x18002cc16  mov     r8, [rbp+3Fh+arg_20]; unsigned __int16 *
0x18002cc1a  lea     rdx, [rbp+3Fh+var_C0+8]; unsigned __int16 **
0x18002cc1e  mov     r9d, edi; int
0x18002cc21  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002cc26  mov     ebx, eax
0x18002cc28  test    eax, eax
0x18002cc2a  js      loc_18002CD23
0x18002cc30  mov     [rbp+3Fh+var_78], esi
0x18002cc33  shr     esi, 4
0x18002cc36  and     esi, edi
0x18002cc38  mov     [rbp+3Fh+arg_28], r14d
0x18002cc3c  mov     dword ptr [rbp+3Fh+var_A0], esi
0x18002cc3f  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18002cc44  test    rax, rax
0x18002cc47  jnz     short loc_18002CC63
0x18002cc49  lea     r8, [rbp+3Fh+arg_28]; int *
0x18002cc4d  mov     edx, edi; int
0x18002cc4f  lea     rcx, [rsp+110h+var_D0]; this
0x18002cc54  call    ?RequestRuntimeDll@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::RequestRuntimeDll(int,int *)
0x18002cc59  mov     ebx, eax
0x18002cc5b  test    eax, eax
0x18002cc5d  js      loc_18002CD18
0x18002cc63  xor     r8d, r8d; int
0x18002cc66  mov     [rsp+110h+hModule], r14
0x18002cc6b  lea     rdx, [rsp+110h+hModule]; HINSTANCE *
0x18002cc70  mov     ecx, edi; int
0x18002cc72  call    ?GetInstallation@@YAJHPEAPEAUHINSTANCE__@@H@Z; GetInstallation(int,HINSTANCE__ * *,int)
0x18002cc77  mov     ebx, eax
0x18002cc79  test    eax, eax
0x18002cc7b  js      loc_18002CD18
0x18002cc81  mov     rcx, [rsp+110h+hModule]; hModule
0x18002cc86  lea     rdx, aDllgetclassobj_1; "DllGetClassObjectInternal"
0x18002cc8d  call    cs:__imp_GetProcAddress
0x18002cc93  test    rax, rax
0x18002cc96  jnz     short loc_18002CCC1
0x18002cc98  call    cs:__imp_GetLastError
0x18002cc9e  cmp     eax, 7Fh
0x18002cca1  jnz     short loc_18002CCBA
0x18002cca3  mov     rcx, [rsp+110h+hModule]; hModule
0x18002cca8  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18002ccaf  call    cs:__imp_GetProcAddress
0x18002ccb5  test    rax, rax
0x18002ccb8  jnz     short loc_18002CCC1
0x18002ccba  mov     ebx, 80131701h
0x18002ccbf  jmp     short loc_18002CD23
0x18002ccc1  mov     rcx, [rbp+3Fh+arg_38]
0x18002ccc8  lea     r8, [rsp+110h+hModule]
0x18002cccd  lea     rdx, IID_IClassFactory
0x18002ccd4  mov     [rsp+110h+hModule], r14
0x18002ccd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccde  mov     ebx, eax
0x18002cce0  test    eax, eax
0x18002cce2  js      short loc_18002CD18
0x18002cce4  mov     rcx, [rsp+110h+hModule]
0x18002cce9  xor     edx, edx
0x18002cceb  mov     r9, [rbp+3Fh+arg_48]
0x18002ccf2  mov     r8, [rbp+3Fh+arg_40]
0x18002ccf9  mov     rax, [rcx]
0x18002ccfc  mov     rax, [rax+18h]
0x18002cd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd05  mov     rcx, [rsp+110h+hModule]
0x18002cd0a  mov     ebx, eax
0x18002cd0c  mov     rax, [rcx]
0x18002cd0f  mov     rax, [rax+10h]
0x18002cd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd18  test    ebx, ebx
0x18002cd1a  jnz     short loc_18002CD23
0x18002cd1c  cmp     [rbp+3Fh+arg_28], r14d
0x18002cd20  cmovz   ebx, edi
0x18002cd23  lea     rcx, [rsp+110h+var_D0]; this
0x18002cd28  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002cd2d  mov     eax, ebx
0x18002cd2f  add     rsp, 0D8h
0x18002cd36  pop     r15
0x18002cd38  pop     r14
0x18002cd3a  pop     r13
0x18002cd3c  pop     r12
0x18002cd3e  pop     rdi
0x18002cd3f  pop     rsi
0x18002cd40  pop     rbx
0x18002cd41  pop     rbp
0x18002cd42  retn
```
