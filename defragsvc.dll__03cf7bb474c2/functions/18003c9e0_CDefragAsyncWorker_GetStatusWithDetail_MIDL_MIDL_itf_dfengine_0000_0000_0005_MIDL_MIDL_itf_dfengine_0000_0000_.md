# CDefragAsyncWorker::GetStatusWithDetail(__MIDL___MIDL_itf_dfengine_0000_0000_0005,__MIDL___MIDL_itf_dfengine_0000_0000_0007 *)

- ea: `0x18003c9e0`
- end: `0x18003cedb`
- name: `?GetStatusWithDetail@CDefragAsyncWorker@@UEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0005@@PEAU__MIDL___MIDL_itf_dfengine_0000_0000_0007@@@Z`
- size: `1275`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x18001913c`
- `0x18001ff18`
- `0x18003c9e0`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cac9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cd52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cd52`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDefragAsyncWorker::GetStatusWithDetail(__int64 a1, int a2, __int64 a3)
{
  __int16 v6; // ax
  unsigned int v7; // ebx
  __int16 v8; // ax
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v11; // [rsp+24h] [rbp-DCh]
  __int16 v12; // [rsp+26h] [rbp-DAh]
  LPVOID v13[2]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v14[2]; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v15[2]; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v16[2]; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v17[3]; // [rsp+98h] [rbp-68h] BYREF
  __m256i v18; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v19; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v20; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v21; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v22; // [rsp+100h] [rbp+0h] BYREF
  __int128 v23; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v24[2]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v25[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v26[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v27; // [rsp+150h] [rbp+50h] BYREF
  __int128 v28; // [rsp+160h] [rbp+60h] BYREF
  __int128 v29; // [rsp+170h] [rbp+70h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CDefragAsyncWorker::GetStatusWithDetail", 1298, 1);
  memset_0(&v18, 0, 0xD0u);
  v17[0] = (LPVOID)&qword_18006F470;
  v17[1] = 0;
  v16[0] = (LPVOID)&qword_18006F470;
  v16[1] = 0;
  v15[0] = (LPVOID)&qword_18006F470;
  v15[1] = 0;
  v14[0] = (LPVOID)&qword_18006F470;
  v14[1] = 0;
  v13[0] = (LPVOID)&qword_18006F470;
  v13[1] = 0;
  v6 = 1307;
  if ( a3 )
  {
    v11 = 1307;
    v6 = 1309;
    if ( a2 )
    {
      v10 = 0;
      v11 = 1309;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
      HIDWORD(v22) = *(_DWORD *)(a1 + 308);
      v18.m256i_i32[1] = *(_DWORD *)(a1 + 88);
      v18.m256i_i32[7] = *(_DWORD *)(a1 + 100);
      DWORD2(v19) = *(_DWORD *)(a1 + 104);
      v18.m256i_i32[0] = *(_DWORD *)(a1 + 108);
      *((_QWORD *)&v23 + 1) = 0;
      *(_OWORD *)((char *)&v18.m256i_u64[1] + 4) = *(_OWORD *)(a1 + 144);
      v18.m256i_i32[2] = *(_DWORD *)(a1 + 84);
      LODWORD(v20) = *(_DWORD *)(a1 + 292);
      HIDWORD(v19) = *(_DWORD *)(a1 + 288);
      DWORD1(v20) = *(_DWORD *)(a1 + 296);
      v26[1] = *(unsigned __int16 **)(a1 + 300);
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 200) + 56LL))(
              *(_QWORD *)(a1 + 200),
              &v19);
      v8 = 1330;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1330;
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 200) + 40LL))(
              *(_QWORD *)(a1 + 200),
              (char *)&v19 + 4);
      v8 = 1331;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1331;
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 200) + 72LL))(
              *(_QWORD *)(a1 + 200),
              (char *)&v20 + 8);
      v8 = 1332;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1332;
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 200) + 88LL))(
              *(_QWORD *)(a1 + 200),
              (char *)&v21 + 8);
      v8 = 1333;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1333;
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 200) + 104LL))(
              *(_QWORD *)(a1 + 200),
              (char *)&v22 + 8);
      v8 = 1334;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1334;
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 200) + 120LL))(
              *(_QWORD *)(a1 + 200),
              &v23);
      v8 = 1335;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1335;
      v10 = CBsString::Set((CBsString *)v17, *(const unsigned __int16 **)(a1 + 208));
      v8 = 1338;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1338;
      v10 = CBsString::Set((CBsString *)v14, *(const unsigned __int16 **)(a1 + 256));
      v8 = 1341;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1341;
      v10 = CBsString::Set((CBsString *)v16, *(const unsigned __int16 **)(a1 + 224));
      v8 = 1344;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1344;
      v10 = CBsString::Set((CBsString *)v15, *(const unsigned __int16 **)(a1 + 240));
      v8 = 1347;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1347;
      v10 = CBsString::Set((CBsString *)v13, *(const unsigned __int16 **)(a1 + 272));
      v8 = 1350;
      if ( v10 < 0 )
        goto LABEL_5;
      v11 = 1350;
      CBsString::Detach((CBsString *)v17, v24);
      CBsString::Detach((CBsString *)v16, &v24[1]);
      CBsString::Detach((CBsString *)v15, v25);
      CBsString::Detach((CBsString *)v14, &v25[1]);
      CBsString::Detach((CBsString *)v13, v26);
      if ( a2 == 2 )
      {
        *(_QWORD *)&v27 = CoTaskMemAlloc(0x280u);
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 200) + 24LL))(*(_QWORD *)(a1 + 200), v27);
        v8 = 1362;
        if ( v10 < 0 )
          goto LABEL_5;
        v11 = 1362;
        v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 200) + 144LL))(
                *(_QWORD *)(a1 + 200),
                (char *)&v27 + 8);
        v8 = 1363;
        if ( v10 < 0 )
          goto LABEL_5;
        v11 = 1363;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int128 *))(**(_QWORD **)(a1 + 200) + 160LL))(
              *(_QWORD *)(a1 + 200),
              &v28,
              &v29);
      v8 = 1368;
      if ( v10 >= 0 )
      {
        v11 = 1368;
        *(__m256i *)a3 = v18;
        *(_OWORD *)(a3 + 32) = v19;
        *(_OWORD *)(a3 + 48) = v20;
        *(_OWORD *)(a3 + 64) = v21;
        *(_OWORD *)(a3 + 80) = v22;
        *(_OWORD *)(a3 + 96) = v23;
        *(_OWORD *)(a3 + 112) = *(_OWORD *)v24;
        *(_OWORD *)(a3 + 128) = *(_OWORD *)v25;
        *(_OWORD *)(a3 + 144) = *(_OWORD *)v26;
        *(_OWORD *)(a3 + 160) = v27;
        *(_OWORD *)(a3 + 176) = v28;
        *(_OWORD *)(a3 + 192) = v29;
        goto LABEL_22;
      }
LABEL_5:
      v12 = v8;
LABEL_22:
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
      v7 = v10;
      goto LABEL_23;
    }
  }
  v7 = -2147024809;
  v10 = -2147024809;
  v12 = v6;
LABEL_23:
  CBsString::_Release(v13);
  CBsString::_Release(v14);
  CBsString::_Release(v15);
  CBsString::_Release(v16);
  CBsString::_Release(v17);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v7;
}

```

## disassembly

```asm
0x18003c9e0  mov     [rsp-8+arg_8], rbx
0x18003c9e5  mov     [rsp-8+arg_18], rsi
0x18003c9ea  push    rbp
0x18003c9eb  push    rdi
0x18003c9ec  push    r14
0x18003c9ee  lea     rbp, [rsp-90h]
0x18003c9f6  sub     rsp, 190h
0x18003c9fd  mov     rax, cs:__security_cookie
0x18003ca04  xor     rax, rsp
0x18003ca07  mov     [rbp+0A0h+var_20], rax
0x18003ca0e  mov     rdi, r8
0x18003ca11  mov     esi, edx
0x18003ca13  mov     rbx, rcx
0x18003ca16  mov     r9d, 1; unsigned __int16
0x18003ca1c  mov     r8d, 512h; unsigned __int16
0x18003ca22  lea     rdx, aCdefragasyncwo_24; "CDefragAsyncWorker::GetStatusWithDetail"
0x18003ca29  lea     rcx, [rsp+1A0h+var_180]; this
0x18003ca2e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003ca33  nop
0x18003ca34  xor     edx, edx; Val
0x18003ca36  mov     r8d, 0D0h; Size
0x18003ca3c  lea     rcx, [rbp+0A0h+var_F0]; void *
0x18003ca40  call    memset_0
0x18003ca45  lea     rax, qword_18006F470
0x18003ca4c  mov     [rbp+0A0h+var_108], rax
0x18003ca50  mov     [rbp+0A0h+var_100], 0
0x18003ca58  mov     [rbp+0A0h+var_118], rax
0x18003ca5c  mov     [rbp+0A0h+var_110], 0
0x18003ca64  mov     [rsp+1A0h+var_128], rax
0x18003ca69  mov     [rbp+0A0h+var_120], 0
0x18003ca71  mov     [rsp+1A0h+var_138], rax
0x18003ca76  mov     [rsp+1A0h+var_130], 0
0x18003ca7f  mov     [rsp+1A0h+var_148], rax
0x18003ca84  mov     [rsp+1A0h+var_140], 0
0x18003ca8d  mov     eax, 51Bh
0x18003ca92  test    rdi, rdi
0x18003ca95  jnz     short loc_18003CAAA
0x18003ca97  mov     ebx, 80070057h
0x18003ca9c  mov     [rsp+1A0h+var_180], ebx
0x18003caa0  mov     [rsp+1A0h+var_17A], ax
0x18003caa5  jmp     loc_18003CE73
0x18003caaa  mov     [rsp+1A0h+var_17C], ax
0x18003caaf  mov     eax, 51Dh
0x18003cab4  test    esi, esi
0x18003cab6  jz      short loc_18003CA97
0x18003cab8  mov     [rsp+1A0h+var_180], 0
0x18003cac0  mov     [rsp+1A0h+var_17C], ax
0x18003cac5  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003cac9  call    cs:__imp_EnterCriticalSection
0x18003cacf  mov     eax, [rbx+134h]
0x18003cad5  mov     [rbp+0A0h+var_94], eax
0x18003cad8  mov     eax, [rbx+58h]
0x18003cadb  mov     dword ptr [rbp+0A0h+var_F0+4], eax
0x18003cade  mov     eax, [rbx+64h]
0x18003cae1  mov     [rbp+0A0h+var_D4], eax
0x18003cae4  mov     eax, [rbx+68h]
0x18003cae7  mov     dword ptr [rbp+0A0h+var_D0+8], eax
0x18003caea  mov     eax, [rbx+6Ch]
0x18003caed  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18003caf0  mov     qword ptr [rbp+0A0h+var_90+8], 0
0x18003caf8  movups  xmm0, xmmword ptr [rbx+90h]
0x18003caff  movdqu  [rbp+0A0h+var_F0+0Ch], xmm0
0x18003cb04  mov     eax, [rbx+54h]
0x18003cb07  mov     dword ptr [rbp+0A0h+var_F0+8], eax
0x18003cb0a  mov     eax, [rbx+124h]
0x18003cb10  mov     dword ptr [rbp+0A0h+var_C0], eax
0x18003cb13  mov     eax, [rbx+120h]
0x18003cb19  mov     dword ptr [rbp+0A0h+var_D0+0Ch], eax
0x18003cb1c  mov     eax, [rbx+128h]
0x18003cb22  mov     dword ptr [rbp+0A0h+var_C0+4], eax
0x18003cb25  mov     eax, [rbx+12Ch]
0x18003cb2b  mov     dword ptr [rbp+0A0h+var_60+8], eax
0x18003cb2e  mov     eax, [rbx+130h]
0x18003cb34  mov     dword ptr [rbp+0A0h+var_60+0Ch], eax
0x18003cb37  mov     rcx, [rbx+0C8h]
0x18003cb3e  mov     rax, [rcx]
0x18003cb41  lea     rdx, [rbp+0A0h+var_D0]
0x18003cb45  mov     rax, [rax+38h]
0x18003cb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb4e  mov     [rsp+1A0h+var_180], eax
0x18003cb52  test    eax, eax
0x18003cb54  mov     eax, 532h
0x18003cb59  jns     short loc_18003CB65
0x18003cb5b  mov     [rsp+1A0h+var_17A], ax
0x18003cb60  jmp     loc_18003CE65
0x18003cb65  mov     [rsp+1A0h+var_17C], ax
0x18003cb6a  mov     rcx, [rbx+0C8h]
0x18003cb71  mov     rax, [rcx]
0x18003cb74  lea     rdx, [rbp+0A0h+var_D0+4]
0x18003cb78  mov     rax, [rax+28h]
0x18003cb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb81  mov     [rsp+1A0h+var_180], eax
0x18003cb85  test    eax, eax
0x18003cb87  mov     eax, 533h
0x18003cb8c  js      short loc_18003CB5B
0x18003cb8e  mov     [rsp+1A0h+var_17C], ax
0x18003cb93  mov     rcx, [rbx+0C8h]
0x18003cb9a  mov     rax, [rcx]
0x18003cb9d  lea     rdx, [rbp+0A0h+var_C0+8]
0x18003cba1  mov     rax, [rax+48h]
0x18003cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbaa  mov     [rsp+1A0h+var_180], eax
0x18003cbae  test    eax, eax
0x18003cbb0  mov     eax, 534h
0x18003cbb5  js      short loc_18003CB5B
0x18003cbb7  mov     [rsp+1A0h+var_17C], ax
0x18003cbbc  mov     rcx, [rbx+0C8h]
0x18003cbc3  mov     rax, [rcx]
0x18003cbc6  lea     rdx, [rbp+0A0h+var_A8]
0x18003cbca  mov     rax, [rax+58h]
0x18003cbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbd3  mov     [rsp+1A0h+var_180], eax
0x18003cbd7  test    eax, eax
0x18003cbd9  mov     eax, 535h
0x18003cbde  js      loc_18003CB5B
0x18003cbe4  mov     [rsp+1A0h+var_17C], ax
0x18003cbe9  mov     rcx, [rbx+0C8h]
0x18003cbf0  mov     rax, [rcx]
0x18003cbf3  lea     rdx, [rbp+0A0h+var_98]
0x18003cbf7  mov     rax, [rax+68h]
0x18003cbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc00  mov     [rsp+1A0h+var_180], eax
0x18003cc04  test    eax, eax
0x18003cc06  mov     eax, 536h
0x18003cc0b  js      loc_18003CB5B
0x18003cc11  mov     [rsp+1A0h+var_17C], ax
0x18003cc16  mov     rcx, [rbx+0C8h]
0x18003cc1d  mov     rax, [rcx]
0x18003cc20  lea     rdx, [rbp+0A0h+var_90]
0x18003cc24  mov     rax, [rax+78h]
0x18003cc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc2d  mov     [rsp+1A0h+var_180], eax
0x18003cc31  test    eax, eax
0x18003cc33  mov     eax, 537h
0x18003cc38  js      loc_18003CB5B
0x18003cc3e  mov     [rsp+1A0h+var_17C], ax
0x18003cc43  mov     rdx, [rbx+0D0h]; unsigned __int16 *
0x18003cc4a  lea     rcx, [rbp+0A0h+var_108]; this
0x18003cc4e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003cc53  mov     [rsp+1A0h+var_180], eax
0x18003cc57  test    eax, eax
0x18003cc59  mov     eax, 53Ah
0x18003cc5e  js      loc_18003CB5B
0x18003cc64  mov     [rsp+1A0h+var_17C], ax
0x18003cc69  mov     rdx, [rbx+100h]; unsigned __int16 *
0x18003cc70  lea     rcx, [rsp+1A0h+var_138]; this
0x18003cc75  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003cc7a  mov     [rsp+1A0h+var_180], eax
0x18003cc7e  test    eax, eax
0x18003cc80  mov     eax, 53Dh
0x18003cc85  js      loc_18003CB5B
0x18003cc8b  mov     [rsp+1A0h+var_17C], ax
0x18003cc90  mov     rdx, [rbx+0E0h]; unsigned __int16 *
0x18003cc97  lea     rcx, [rbp+0A0h+var_118]; this
0x18003cc9b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003cca0  mov     [rsp+1A0h+var_180], eax
0x18003cca4  test    eax, eax
0x18003cca6  mov     eax, 540h
0x18003ccab  js      loc_18003CB5B
0x18003ccb1  mov     [rsp+1A0h+var_17C], ax
0x18003ccb6  mov     rdx, [rbx+0F0h]; unsigned __int16 *
0x18003ccbd  lea     rcx, [rsp+1A0h+var_128]; this
0x18003ccc2  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003ccc7  mov     [rsp+1A0h+var_180], eax
0x18003cccb  test    eax, eax
0x18003cccd  mov     eax, 543h
0x18003ccd2  js      loc_18003CB5B
0x18003ccd8  mov     [rsp+1A0h+var_17C], ax
0x18003ccdd  mov     rdx, [rbx+110h]; unsigned __int16 *
0x18003cce4  lea     rcx, [rsp+1A0h+var_148]; this
0x18003cce9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003ccee  mov     [rsp+1A0h+var_180], eax
0x18003ccf2  test    eax, eax
0x18003ccf4  mov     eax, 546h
0x18003ccf9  js      loc_18003CB5B
0x18003ccff  mov     [rsp+1A0h+var_17C], ax
0x18003cd04  lea     rdx, [rbp+0A0h+var_80]; unsigned __int16 **
0x18003cd08  lea     rcx, [rbp+0A0h+var_108]; this
0x18003cd0c  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003cd11  lea     rdx, [rbp+0A0h+var_80+8]; unsigned __int16 **
0x18003cd15  lea     rcx, [rbp+0A0h+var_118]; this
0x18003cd19  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003cd1e  lea     rdx, [rbp+0A0h+var_70]; unsigned __int16 **
0x18003cd22  lea     rcx, [rsp+1A0h+var_128]; this
0x18003cd27  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003cd2c  lea     rdx, [rbp+0A0h+var_70+8]; unsigned __int16 **
0x18003cd30  lea     rcx, [rsp+1A0h+var_138]; this
0x18003cd35  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003cd3a  lea     rdx, [rbp+0A0h+var_60]; unsigned __int16 **
0x18003cd3e  lea     rcx, [rsp+1A0h+var_148]; this
0x18003cd43  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18003cd48  cmp     esi, 2
0x18003cd4b  jnz     short loc_18003CDBB
0x18003cd4d  mov     ecx, 280h; cb
0x18003cd52  call    cs:__imp_CoTaskMemAlloc
0x18003cd58  mov     rdx, rax
0x18003cd5b  mov     qword ptr [rbp+0A0h+var_50], rax
0x18003cd5f  mov     r8, [rbx+0C8h]
0x18003cd66  mov     rcx, [r8]
0x18003cd69  mov     rax, [rcx+18h]
0x18003cd6d  mov     rcx, r8
0x18003cd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd75  mov     [rsp+1A0h+var_180], eax
0x18003cd79  test    eax, eax
0x18003cd7b  mov     eax, 552h
0x18003cd80  js      loc_18003CB5B
0x18003cd86  mov     [rsp+1A0h+var_17C], ax
0x18003cd8b  mov     rcx, [rbx+0C8h]
0x18003cd92  mov     rax, [rcx]
0x18003cd95  lea     rdx, [rbp+0A0h+var_50+8]
0x18003cd99  mov     rax, [rax+90h]
0x18003cda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cda5  mov     [rsp+1A0h+var_180], eax
0x18003cda9  test    eax, eax
0x18003cdab  mov     eax, 553h
0x18003cdb0  js      loc_18003CB5B
0x18003cdb6  mov     [rsp+1A0h+var_17C], ax
0x18003cdbb  mov     rcx, [rbx+0C8h]
0x18003cdc2  mov     rax, [rcx]
0x18003cdc5  lea     r8, [rbp+0A0h+var_30]
0x18003cdc9  lea     rdx, [rbp+0A0h+var_40]
0x18003cdcd  mov     rax, [rax+0A0h]
0x18003cdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdd9  mov     [rsp+1A0h+var_180], eax
0x18003cddd  test    eax, eax
0x18003cddf  mov     eax, 558h
0x18003cde4  js      loc_18003CB5B
0x18003cdea  mov     [rsp+1A0h+var_17C], ax
0x18003cdef  movaps  xmm0, [rbp+0A0h+var_F0]
0x18003cdf3  movups  xmmword ptr [rdi], xmm0
0x18003cdf6  movaps  xmm1, xmmword ptr [rbp-40h]
0x18003cdfa  movups  xmmword ptr [rdi+10h], xmm1
0x18003cdfe  movaps  xmm0, [rbp+0A0h+var_D0]
0x18003ce02  movups  xmmword ptr [rdi+20h], xmm0
0x18003ce06  movaps  xmm1, [rbp+0A0h+var_C0]
0x18003ce0a  movups  xmmword ptr [rdi+30h], xmm1
0x18003ce0e  movaps  xmm0, xmmword ptr [rbp-10h]
0x18003ce12  movups  xmmword ptr [rdi+40h], xmm0
0x18003ce16  movaps  xmm1, xmmword ptr [rbp+0]
0x18003ce1a  movups  xmmword ptr [rdi+50h], xmm1
0x18003ce1e  movaps  xmm0, [rbp+0A0h+var_90]
0x18003ce22  movups  xmmword ptr [rdi+60h], xmm0
0x18003ce26  movaps  xmm1, xmmword ptr [rbp+0A0h+var_80]
0x18003ce2a  movups  xmmword ptr [rdi+70h], xmm1
0x18003ce2e  movaps  xmm0, xmmword ptr [rbp+0A0h+var_70]
0x18003ce32  movups  xmmword ptr [rdi+80h], xmm0
0x18003ce39  movaps  xmm1, xmmword ptr [rbp+0A0h+var_60]
0x18003ce3d  movups  xmmword ptr [rdi+90h], xmm1
0x18003ce44  movaps  xmm0, [rbp+0A0h+var_50]
0x18003ce48  movups  xmmword ptr [rdi+0A0h], xmm0
0x18003ce4f  movaps  xmm1, [rbp+0A0h+var_40]
0x18003ce53  movups  xmmword ptr [rdi+0B0h], xmm1
0x18003ce5a  movaps  xmm0, [rbp+0A0h+var_30]
0x18003ce5e  movups  xmmword ptr [rdi+0C0h], xmm0
0x18003ce65  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003ce69  call    cs:__imp_LeaveCriticalSection
0x18003ce6f  mov     ebx, [rsp+1A0h+var_180]
0x18003ce73  lea     rcx, [rsp+1A0h+var_148]; this
0x18003ce78  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003ce7d  nop
0x18003ce7e  lea     rcx, [rsp+1A0h+var_138]; this
0x18003ce83  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003ce88  nop
0x18003ce89  lea     rcx, [rsp+1A0h+var_128]; this
0x18003ce8e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003ce93  nop
0x18003ce94  lea     rcx, [rbp+0A0h+var_118]; this
0x18003ce98  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003ce9d  nop
0x18003ce9e  lea     rcx, [rbp+0A0h+var_108]; this
0x18003cea2  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003cea7  nop
0x18003cea8  lea     rcx, [rsp+1A0h+var_180]; this
0x18003cead  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003ceb2  mov     eax, ebx
0x18003ceb4  mov     rcx, [rbp+0A0h+var_20]
0x18003cebb  xor     rcx, rsp; StackCookie
0x18003cebe  call    __security_check_cookie
0x18003cec3  lea     r11, [rsp+1A0h+var_10]
0x18003cecb  mov     rbx, [r11+28h]
0x18003cecf  mov     rsi, [r11+38h]
0x18003ced3  mov     rsp, r11
0x18003ced6  pop     r14
0x18003ced8  pop     rdi
0x18003ced9  pop     rbp
0x18003ceda  retn
```
