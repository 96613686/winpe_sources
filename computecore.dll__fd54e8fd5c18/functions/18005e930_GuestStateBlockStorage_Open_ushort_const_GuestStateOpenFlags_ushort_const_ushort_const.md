# GuestStateBlockStorage::Open(ushort const *,GuestStateOpenFlags,ushort const *,ushort const *)

- ea: `0x18005e930`
- end: `0x18005ed4f`
- name: `?Open@GuestStateBlockStorage@@UEAA_NPEBGW4GuestStateOpenFlags@@00@Z`
- size: `1055`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800016ec`
- `0x1800067c0`
- `0x180009e8c`
- `0x18001017c`
- `0x180011894`
- `0x1800136d0`
- `0x180020c90`
- `0x180027310`
- `0x180055e2c`
- `0x18005d2dc`
- `0x18005e5a0`
- `0x18005e930`
- `0x18005f35c`
- `0x18009739c`
- `0x1800992f8`
- `0x1800993f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ec93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ec93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ec8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ecc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ec8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ecc4`

## string_xrefs

- `0x18005eacd`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005ed18`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005ed29`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005ed3b`: `onecore\vm\common\gueststate\gueststateblockstorage.cpp`
- `0x18005eb2c`: `GuestStateBlockStorage::Open`
- `0x18005ed11`: `Failed to open file "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall GuestStateBlockStorage::Open(__int64 a1, const char *a2, __int64 a3, __int64 a4, unsigned __int16 *a5)
{
  int v6; // r13d
  __int64 *v9; // r14
  signed int v10; // ebx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  int v13; // edi
  bool v14; // al
  char result; // al
  __int128 *v16; // rcx
  __int64 v17; // rdx
  struct _OVERLAPPED *v18; // r8
  __int64 v19; // r9
  __int64 DeviceVHDEx; // r14
  const char *v21; // r9
  const char *v22; // r9
  __int64 v23; // r8
  __int64 v24; // r8
  void **v25; // r15
  void *v26; // r13
  DWORD LastError; // ebx
  const char *v28; // rax
  int nInBufferSize; // [rsp+20h] [rbp-128h]
  unsigned int *v30; // [rsp+38h] [rbp-110h]
  int v31; // [rsp+40h] [rbp-108h] BYREF
  __int64 v32; // [rsp+48h] [rbp-100h] BYREF
  __int64 v33; // [rsp+50h] [rbp-F8h] BYREF
  GuestStateBlockStorage *v34; // [rsp+58h] [rbp-F0h]
  __int128 v35; // [rsp+60h] [rbp-E8h] BYREF
  __int128 v36; // [rsp+70h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+80h] [rbp-C8h]
  struct _EVENT_DATA_DESCRIPTOR v38[2]; // [rsp+90h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+B0h] [rbp-98h] BYREF
  __int64 *v40; // [rsp+D0h] [rbp-78h]
  int v41; // [rsp+D8h] [rbp-70h]
  int v42; // [rsp+DCh] [rbp-6Ch]
  int *v43; // [rsp+E0h] [rbp-68h]
  __int64 v44; // [rsp+E8h] [rbp-60h]
  __int64 *v45; // [rsp+F0h] [rbp-58h]
  __int64 v46; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v6 = a3;
  v31 = a3;
  v34 = (GuestStateBlockStorage *)a1;
  v9 = (__int64 *)a5;
  v36 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36) = 0;
  try
  {
    if ( (unsigned int)ValidateFile((const WCHAR *)a2, (__int64)a2, a3, a4, (__int64)&v36) )
    {
      Vml::VmGuid::Assign((Vml::VmGuid *)&v35, a5);
      v16 = &v36;
      if ( si128.m128i_i64[1] > 7uLL )
        v16 = (__int128 *)v36;
      DeviceVHDEx = CreateDeviceVHDEx(v16, ((unsigned __int8)!(v6 & 1) << 8) + 3);
      v32 = DeviceVHDEx;
      if ( ((DeviceVHDEx + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v28 = (const char *)std::wstring::c_str(&v36, v17, v18, v19);
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
          "Failed to open file \"%ws\"",
          v28,
          "GuestStateBlockStorage::Open",
          90);
      }
      if ( (v6 & 1) == 0 && !(unsigned int)SyncDeviceIoControl((HANDLE)DeviceVHDEx, 0x248260u, v18, 0, 0, 0, 0, v30) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
          v21);
      memset(v38, 0, sizeof(v38));
      LODWORD(v38[0].Ptr) = 1;
      if ( !(unsigned int)SyncDeviceIoControl(
                            (HANDLE)DeviceVHDEx,
                            0x2401A0u,
                            v18,
                            v38,
                            0x20u,
                            (void *)(a1 + 152),
                            0x10u,
                            v30) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
          v22);
      *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 152) / (unsigned __int64)*(unsigned int *)(a1 + 160);
      if ( a4 )
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(a4 + 2 * v23) );
        std::wstring::_Assign<unsigned short>(a1 + 80, a4);
      }
      *(_OWORD *)(a1 + 112) = v35;
      std::wstring::operator=(a1 + 8, &v36);
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)&a2[2 * v24] );
      std::wstring::_Assign<unsigned short>(a1 + 40, a2);
      *(_DWORD *)(a1 + 72) = v6 & 0x7FFFFFFF;
      v25 = (void **)(a1 + 136);
      if ( (__int64 *)(a1 + 136) != &v32 )
      {
        v26 = *v25;
        if ( (char *)*v25 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          LastError = GetLastError();
          CloseHandle(v26);
          SetLastError(LastError);
        }
        *v25 = (void *)DeviceVHDEx;
        DeviceVHDEx = -1;
        v32 = -1;
        v6 = v31;
      }
      if ( v6 >= 0 )
        GuestStateBlockStorage::Mount((GuestStateBlockStorage *)a1);
      if ( (unsigned __int64)(DeviceVHDEx - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)DeviceVHDEx);
      std::wstring::~wstring(&v36);
      result = 1;
    }
    else
    {
      v10 = GetLastError();
      v11 = GuestStateFileTraceProvider::Provider();
      if ( *(_DWORD *)v11 > 5u
        && (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v11 + 3) & 0x400000000000LL) == *((_QWORD *)v11 + 3) )
      {
        v33 = 0x1000000;
        v31 = v10;
        v45 = &v33;
        v46 = 8;
        v43 = &v31;
        v44 = 4;
        if ( a5 )
        {
          v12 = -1;
          do
            ++v12;
          while ( a5[v12] );
          v13 = 2 * v12 + 2;
        }
        else
        {
          v9 = &qword_1800AD7F8;
          v13 = 2;
        }
        v40 = v9;
        v41 = v13;
        v42 = 0;
        tlgWriteTransfer_EventWriteTransfer((int)v11, (int)&word_1800CAAC6, 0, 0, 5u, &v39);
      }
      v14 = v10 != 2;
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      LOBYTE(nInBufferSize) = v14;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststateblockstorage.cpp",
        (const char *)(unsigned int)v10,
        nInBufferSize,
        (bool)"Validation failed for file \"%ws\"",
        a2);
      std::wstring::~wstring(&v36);
      result = 0;
    }
  }
  catch ( ... )
  {
    GuestStateBlockStorage::Close(v34);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18005e930  push    rbx
0x18005e932  push    rsi
0x18005e933  push    rdi
0x18005e934  push    r12
0x18005e936  push    r13
0x18005e938  push    r14
0x18005e93a  push    r15
0x18005e93c  sub     rsp, 110h
0x18005e943  mov     rax, cs:__security_cookie
0x18005e94a  xor     rax, rsp
0x18005e94d  mov     [rsp+148h+var_48], rax
0x18005e955  mov     r15, r9
0x18005e958  mov     r13d, r8d
0x18005e95b  mov     [rsp+148h+var_108], r8d
0x18005e960  mov     r12, rdx
0x18005e963  mov     rsi, rcx
0x18005e966  mov     [rsp+148h+var_F0], rcx
0x18005e96b  mov     r14, [rsp+148h+arg_20]
0x18005e973  xorps   xmm0, xmm0
0x18005e976  movups  [rsp+148h+var_D8], xmm0
0x18005e97b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005e983  movdqu  [rsp+148h+var_C8], xmm1
0x18005e98c  xor     edi, edi
0x18005e98e  mov     word ptr [rsp+148h+var_D8], di
0x18005e993  lea     rax, [rsp+148h+var_D8]
0x18005e998  mov     qword ptr [rsp+148h+nInBufferSize], rax
0x18005e99d  mov     rcx, rdx
0x18005e9a0  call    ?ValidateFile@@YAHPEBGKKPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ValidateFile(ushort const *,ulong,ulong,void *,std::wstring &)
0x18005e9a5  test    eax, eax
0x18005e9a7  jnz     loc_18005EAF0
0x18005e9ad  call    cs:__imp_GetLastError
0x18005e9b3  mov     ebx, eax
0x18005e9b5  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005e9ba  mov     ecx, [rax]
0x18005e9bc  cmp     ecx, 5
0x18005e9bf  jbe     loc_18005EA9A
0x18005e9c5  mov     rdx, [rax+18h]
0x18005e9c9  mov     rcx, [rax+10h]
0x18005e9cd  mov     r8, 400000000000h
0x18005e9d7  test    r8, rcx
0x18005e9da  jz      loc_18005EA9A
0x18005e9e0  mov     rcx, rdx
0x18005e9e3  and     rcx, r8
0x18005e9e6  cmp     rcx, rdx
0x18005e9e9  jnz     loc_18005EA9A
0x18005e9ef  mov     [rsp+148h+var_F8], 1000000h
0x18005e9f8  mov     [rsp+148h+var_108], ebx
0x18005e9fc  lea     rcx, [rsp+148h+var_F8]
0x18005ea01  mov     [rsp+148h+var_58], rcx
0x18005ea09  mov     [rsp+148h+var_50], 8
0x18005ea15  lea     rcx, [rsp+148h+var_108]
0x18005ea1a  mov     [rsp+148h+var_68], rcx
0x18005ea22  mov     [rsp+148h+var_60], 4
0x18005ea2e  test    r14, r14
0x18005ea31  jz      short loc_18005EA4C
0x18005ea33  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ea37  xor     ecx, ecx
0x18005ea39  inc     rdi
0x18005ea3c  cmp     [r14+rdi*2], cx
0x18005ea41  jnz     short loc_18005EA39
0x18005ea43  lea     edi, ds:2[rdi*2]
0x18005ea4a  jmp     short loc_18005EA58
0x18005ea4c  lea     r14, qword_1800AD7F8
0x18005ea53  mov     edi, 2
0x18005ea58  mov     [rsp+148h+var_78], r14
0x18005ea60  mov     [rsp+148h+var_70], edi
0x18005ea67  xor     edi, edi
0x18005ea69  mov     [rsp+148h+var_6C], edi
0x18005ea70  lea     rcx, [rsp+148h+var_98]
0x18005ea78  mov     [rsp+148h+var_120], rcx; PEVENT_DATA_DESCRIPTOR
0x18005ea7d  mov     [rsp+148h+nInBufferSize], 5; ULONG
0x18005ea85  xor     r9d, r9d; int
0x18005ea88  xor     r8d, r8d; int
0x18005ea8b  lea     rdx, word_1800CAAC6; int
0x18005ea92  mov     rcx, rax; int
0x18005ea95  call    _tlgWriteTransfer_EventWriteTransfer
0x18005ea9a  cmp     ebx, 2
0x18005ea9d  setnz   al
0x18005eaa0  test    ebx, ebx
0x18005eaa2  jle     short loc_18005EAAD
0x18005eaa4  movzx   ebx, bx
0x18005eaa7  or      ebx, 80070000h
0x18005eaad  mov     rcx, [rsp+148h]; this
0x18005eab5  mov     [rsp+148h+var_118], r12; char *
0x18005eaba  lea     rdx, aValidationFail; "Validation failed for file \"%ws\""
0x18005eac1  mov     [rsp+148h+var_120], rdx; bool
0x18005eac6  mov     byte ptr [rsp+148h+nInBufferSize], al; int
0x18005eaca  mov     r9d, ebx; char *
0x18005eacd  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005ead4  mov     edx, 4Eh ; 'N'; void *
0x18005ead9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005eade  nop
0x18005eadf  lea     rcx, [rsp+148h+var_D8]
0x18005eae4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005eae9  xor     al, al
0x18005eaeb  jmp     loc_18005ECD7
0x18005eaf0  mov     rdx, r14; unsigned __int16 *
0x18005eaf3  lea     rcx, [rsp+148h+var_E8]; this
0x18005eaf8  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x18005eafd  mov     al, r13b
0x18005eb00  and     al, 1
0x18005eb02  movzx   ebx, al
0x18005eb05  mov     edx, ebx
0x18005eb07  xor     edx, 1
0x18005eb0a  shl     edx, 8
0x18005eb0d  add     edx, 3
0x18005eb10  lea     rcx, [rsp+148h+var_D8]
0x18005eb15  cmp     qword ptr [rsp+148h+var_C8+8], 7
0x18005eb1e  cmova   rcx, qword ptr [rsp+148h+var_D8]
0x18005eb24  mov     dword ptr [rsp+148h+var_118], 5Ah ; 'Z'
0x18005eb2c  lea     rax, aGueststatebloc_0; "GuestStateBlockStorage::Open"
0x18005eb33  mov     [rsp+148h+var_120], rax
0x18005eb38  lea     rax, [rsp+148h+var_E8]
0x18005eb3d  mov     qword ptr [rsp+148h+nInBufferSize], rax
0x18005eb42  call    ?CreateDeviceVHDEx@@YAPEAXPEBGKHW4CreateStorageDeviceFlags@@PEBU_GUID@@PEBDK2@Z; CreateDeviceVHDEx(ushort const *,ulong,int,CreateStorageDeviceFlags,_GUID const *,char const *,ulong,_GUID const *)
0x18005eb47  mov     r14, rax
0x18005eb4a  mov     [rsp+148h+var_100], rax
0x18005eb4f  inc     rax
0x18005eb52  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005eb58  jz      loc_18005ECFA
0x18005eb5e  test    bl, bl
0x18005eb60  jnz     short loc_18005EB8F
0x18005eb62  mov     rbx, [rsp+148h]
0x18005eb6a  mov     dword ptr [rsp+148h+var_118], edi; unsigned int
0x18005eb6e  mov     [rsp+148h+var_120], rdi; void *
0x18005eb73  mov     [rsp+148h+nInBufferSize], edi; nInBufferSize
0x18005eb77  xor     r9d, r9d; void *
0x18005eb7a  mov     edx, 248260h; dwIoControlCode
0x18005eb7f  mov     rcx, r14; hFile
0x18005eb82  call    ?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z; SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)
0x18005eb87  test    eax, eax
0x18005eb89  jz      loc_18005ED29
0x18005eb8f  xorps   xmm0, xmm0
0x18005eb92  movups  [rsp+148h+var_B8], xmm0
0x18005eb9a  movups  [rsp+148h+var_A8], xmm0
0x18005eba2  mov     dword ptr [rsp+148h+var_B8], 1
0x18005ebad  lea     rbx, [rsi+98h]
0x18005ebb4  mov     rdi, [rsp+148h]
0x18005ebbc  mov     dword ptr [rsp+148h+var_118], 10h; unsigned int
0x18005ebc4  mov     [rsp+148h+var_120], rbx; void *
0x18005ebc9  mov     [rsp+148h+nInBufferSize], 20h ; ' '; nInBufferSize
0x18005ebd1  lea     r9, [rsp+148h+var_B8]; void *
0x18005ebd9  mov     edx, 2401A0h; dwIoControlCode
0x18005ebde  mov     rcx, r14; hFile
0x18005ebe1  call    ?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z; SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)
0x18005ebe6  test    eax, eax
0x18005ebe8  jz      loc_18005ED3B
0x18005ebee  mov     ecx, [rsi+0A0h]
0x18005ebf4  xor     edx, edx
0x18005ebf6  mov     rax, [rbx]
0x18005ebf9  div     rcx
0x18005ebfc  mov     [rsi+0A8h], rax
0x18005ec03  xor     ebx, ebx
0x18005ec05  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ec09  test    r15, r15
0x18005ec0c  jz      short loc_18005EC27
0x18005ec0e  mov     r8, rdi
0x18005ec11  inc     r8
0x18005ec14  cmp     [r15+r8*2], bx
0x18005ec19  jnz     short loc_18005EC11
0x18005ec1b  lea     rcx, [rsi+50h]
0x18005ec1f  mov     rdx, r15
0x18005ec22  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005ec27  movups  xmm0, [rsp+148h+var_E8]
0x18005ec2c  movdqu  xmmword ptr [rsi+70h], xmm0
0x18005ec31  lea     rcx, [rsi+8]
0x18005ec35  lea     rdx, [rsp+148h+var_D8]
0x18005ec3a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005ec3f  mov     r8, rdi
0x18005ec42  inc     r8
0x18005ec45  cmp     [r12+r8*2], bx
0x18005ec4a  jnz     short loc_18005EC42
0x18005ec4c  lea     rcx, [rsi+28h]
0x18005ec50  mov     rdx, r12
0x18005ec53  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005ec58  mov     eax, r13d
0x18005ec5b  btr     eax, 1Fh
0x18005ec5f  mov     [rsi+48h], eax
0x18005ec62  lea     r15, [rsi+88h]
0x18005ec69  lea     rax, [rsp+148h+var_100]
0x18005ec6e  cmp     r15, rax
0x18005ec71  jz      short loc_18005ECA9
0x18005ec73  mov     r13, [r15]
0x18005ec76  lea     rax, [r13-1]
0x18005ec7a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ec7e  ja      short loc_18005EC99
0x18005ec80  call    cs:__imp_GetLastError
0x18005ec86  mov     ebx, eax
0x18005ec88  mov     rcx, r13; hObject
0x18005ec8b  call    cs:__imp_CloseHandle
0x18005ec91  mov     ecx, ebx; dwErrCode
0x18005ec93  call    cs:__imp_SetLastError
0x18005ec99  mov     [r15], r14
0x18005ec9c  mov     r14, rdi
0x18005ec9f  mov     [rsp+148h+var_100], rdi
0x18005eca4  mov     r13d, [rsp+148h+var_108]
0x18005eca9  test    r13d, r13d
0x18005ecac  js      short loc_18005ECB7
0x18005ecae  mov     rcx, rsi; this
0x18005ecb1  call    ?Mount@GuestStateBlockStorage@@UEAAXXZ; GuestStateBlockStorage::Mount(void)
0x18005ecb6  nop
0x18005ecb7  lea     rdx, [r14-1]
0x18005ecbb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005ecbf  ja      short loc_18005ECCB
0x18005ecc1  mov     rcx, r14; hObject
0x18005ecc4  call    cs:__imp_CloseHandle
0x18005ecca  nop
0x18005eccb  lea     rcx, [rsp+148h+var_D8]
0x18005ecd0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ecd5  mov     al, 1
0x18005ecd7  mov     rcx, [rsp+148h+var_48]
0x18005ecdf  xor     rcx, rsp; StackCookie
0x18005ece2  call    __security_check_cookie
0x18005ece7  add     rsp, 110h
0x18005ecee  pop     r15
0x18005ecf0  pop     r14
0x18005ecf2  pop     r13
0x18005ecf4  pop     r12
0x18005ecf6  pop     rdi
0x18005ecf7  pop     rsi
0x18005ecf8  pop     rbx
0x18005ecf9  retn
0x18005ecfa  lea     rcx, [rsp+148h+var_D8]
0x18005ecff  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005ed04  mov     rcx, [rsp+148h]; this
0x18005ed0c  mov     qword ptr [rsp+148h+nInBufferSize], rax; char *
0x18005ed11  lea     r9, aFailedToOpenFi_2; "Failed to open file \"%ws\""
0x18005ed18  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005ed1f  mov     edx, 5Eh ; '^'; void *
0x18005ed24  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18005ed29  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005ed30  lea     edx, [rax+63h]; void *
0x18005ed33  mov     rcx, rbx; this
0x18005ed36  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005ed3b  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\gueststate\\guests"...
0x18005ed42  lea     edx, [rax+6Bh]; void *
0x18005ed45  mov     rcx, rdi; this
0x18005ed48  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
