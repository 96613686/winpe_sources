# CDeviceInterface::Initialize(void)

- ea: `0x180024764`
- end: `0x180024b92`
- name: `?Initialize@CDeviceInterface@@QEAAJXZ`
- size: `1070`
- prototype: `__int64 __fastcall(CDeviceInterface *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180034d4c`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x1800103e0`
- `0x180010c98`
- `0x180024288`
- `0x180024764`
- `0x180024e18`
- `0x180024fdc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `DEVOBJ!DevObjGetClassDevs` at `0x1800247fb`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800247fb`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002482d`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002482d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800247ba`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800247ba`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180024935`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180024935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024940`

## string_xrefs

- `0x180024a26`: `TelCacheProvider::AddItem failed [%#x]`
- `0x180024acb`: `Telcache is not initialized [%#x]`
- `0x180024955`: `DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]`
- `0x1800249a2`: `DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]`
- `0x1800249d4`: `DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]`
- `0x1800249e5`: `DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]`

## pseudocode

```c
__int64 __fastcall CDeviceInterface::Initialize(CDeviceInterface *this)
{
  __int64 i; // r12
  __int64 DeviceInfoList; // rax
  void *v4; // r15
  char *v5; // r14
  __int64 v6; // r8
  char *v7; // rbx
  CDeviceInterface *v8; // rcx
  __int64 v9; // r8
  _DWORD *v10; // rcx
  __int64 v11; // r8
  CDeviceInterface *v12; // rcx
  signed int LastError; // eax
  unsigned int v14; // ebx
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  int v18; // eax
  int v19; // ebx
  FILE *v20; // rax
  FILE *v21; // rax
  FILE *v22; // rax
  unsigned int v23; // ebx
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  _OWORD v28[3]; // [rsp+30h] [rbp-88h] BYREF

  if ( qword_1801573E8 )
  {
    for ( i = 0; i != 20; ++i )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v4 = (void *)DeviceInfoList;
      if ( DeviceInfoList == -1
        || (v5 = (char *)this + 80 * i, !(unsigned int)DevObjGetClassDevs(DeviceInfoList, v5 + 16, 0, 18, 0, 0)) )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        AslLogCallPrintf(
          2,
          "CDeviceInterface::Initialize",
          125,
          "DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]",
          v14);
        if ( EnableDevInvStdErrLog )
        {
          v15 = o___acrt_iob_func_0(2u);
          fprintf(v15, "Error: %s, %u: ", "CDeviceInterface::Initialize", 125);
          v16 = o___acrt_iob_func_0(2u);
          fprintf(v16, "DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]", v14);
          v17 = o___acrt_iob_func_0(2u);
          fprintf(v17, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]", v14);
        AslLogCallPrintf(
          1,
          "CDeviceInterface::Initialize",
          125,
          "DevObjCreateDeviceInfoList or DevObjGetClassDevs failed with [0x%08x]",
          v14);
      }
      else
      {
        memset(v28, 0, sizeof(v28));
        LODWORD(v28[0]) = 48;
        if ( (unsigned int)DevObjEnumDeviceInfo(v4, 0, v28) )
        {
          v7 = (char *)this + 80 * i + 64;
          if ( *((_QWORD *)v7 + 3) )
          {
            if ( *((_QWORD *)v7 + 3) <= 7u )
              v8 = (CDeviceInterface *)((char *)this + 80 * i + 64);
            else
              v8 = *(CDeviceInterface **)v7;
            *((_QWORD *)v7 + 2) = 1;
            *(_DWORD *)v8 = 49;
          }
          else
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              v7,
              1,
              v6,
              L"1");
          }
          if ( *((_QWORD *)v5 + 2) == *(_QWORD *)&GUID_SensorType_AmbientLight.Data1
            && *((_QWORD *)v5 + 3) == *(_QWORD *)GUID_SensorType_AmbientLight.Data4
            && (unsigned int)CDeviceInterface::IsColorCapable(v8) )
          {
            if ( *((_QWORD *)v7 + 3) )
            {
              if ( *((_QWORD *)v7 + 3) <= 7u )
                v10 = (_DWORD *)((char *)this + 80 * i + 64);
              else
                v10 = *(_DWORD **)v7;
              *((_QWORD *)v7 + 2) = 1;
              *v10 = 50;
            }
            else
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                v7,
                1,
                v9,
                L"2");
            }
          }
          else if ( *((_QWORD *)v5 + 2) == *(_QWORD *)&GUID_SensorType_Proximity.Data1
                 && *((_QWORD *)v5 + 3) == *(_QWORD *)GUID_SensorType_Proximity.Data4
                 && (unsigned int)CDeviceInterface::IsHumanPresenceCapable(v8) )
          {
            if ( *((_QWORD *)v7 + 3) )
            {
              if ( *((_QWORD *)v7 + 3) <= 7u )
                v12 = (CDeviceInterface *)((char *)this + 80 * i + 64);
              else
                v12 = *(CDeviceInterface **)v7;
              *((_QWORD *)v7 + 2) = 1;
              *(_DWORD *)v12 = 50;
            }
            else
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                v7,
                1,
                v11,
                L"2");
            }
            *((_DWORD *)this + 404) = CDeviceInterface::GetPresenceCapabilities(v12, v4);
          }
        }
        DevObjDestroyDeviceInfoList(v4);
      }
    }
    v18 = TelCacheProvider::AddItem((TelCacheProvider *)g_DeviceInterfaceStore, this);
    v19 = v18;
    if ( v18 < 0 )
    {
      AslLogCallPrintf(2, "CDeviceInterface::Initialize", 137, "TelCacheProvider::AddItem failed [%#x]", v18);
      if ( EnableDevInvStdErrLog )
      {
        v20 = o___acrt_iob_func_0(2u);
        fprintf(v20, "Error: %s, %u: ", "CDeviceInterface::Initialize", 137);
        v21 = o___acrt_iob_func_0(2u);
        fprintf(v21, "TelCacheProvider::AddItem failed [%#x]", v19);
        v22 = o___acrt_iob_func_0(2u);
        fprintf(v22, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "TelCacheProvider::AddItem failed [%#x]", v19);
      AslLogCallPrintf(1, "CDeviceInterface::Initialize", 137, "TelCacheProvider::AddItem failed [%#x]", v19);
    }
    return 0;
  }
  else
  {
    v23 = -2147467259;
    AslLogCallPrintf(2, "CDeviceInterface::Initialize", 77, "Telcache is not initialized [%#x]", -2147467259);
    if ( EnableDevInvStdErrLog )
    {
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, "Error: %s, %u: ", "CDeviceInterface::Initialize", 77);
      v25 = o___acrt_iob_func_0(2u);
      fprintf(v25, "Telcache is not initialized [%#x]", -2147467259);
      v26 = o___acrt_iob_func_0(2u);
      fprintf(v26, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Telcache is not initialized [%#x]", -2147467259);
    AslLogCallPrintf(1, "CDeviceInterface::Initialize", 77, "Telcache is not initialized [%#x]", -2147467259);
  }
  return v23;
}

```

## disassembly

```asm
0x180024764  push    rbx
0x180024766  push    rbp
0x180024767  push    rsi
0x180024768  push    rdi
0x180024769  push    r12
0x18002476b  push    r13
0x18002476d  push    r14
0x18002476f  push    r15
0x180024771  sub     rsp, 78h
0x180024775  mov     rax, cs:__security_cookie
0x18002477c  xor     rax, rsp
0x18002477f  mov     [rsp+0B8h+var_58], rax
0x180024784  cmp     cs:qword_1801573E8, 0
0x18002478c  lea     rsi, aCdeviceinterfa_1; "CDeviceInterface::Initialize"
0x180024793  mov     r13, rcx
0x180024796  mov     ebp, 2
0x18002479b  jz      loc_180024ACB
0x1800247a1  xor     r12d, r12d
0x1800247a4  lea     edi, [rbp-1]
0x1800247a7  xor     r9d, r9d
0x1800247aa  mov     [rsp+0B8h+var_98], 0
0x1800247b3  xor     r8d, r8d
0x1800247b6  xor     edx, edx
0x1800247b8  xor     ecx, ecx
0x1800247ba  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800247c0  mov     r15, rax
0x1800247c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800247c7  jz      loc_180024940
0x1800247cd  lea     rbx, [r12+r12*4]
0x1800247d1  mov     [rsp+0B8h+var_90], 0
0x1800247da  shl     rbx, 4
0x1800247de  mov     r9d, 12h
0x1800247e4  xor     r8d, r8d
0x1800247e7  mov     [rsp+0B8h+var_98], 0
0x1800247f0  mov     rcx, rax
0x1800247f3  lea     r14, [rbx+r13]
0x1800247f7  lea     rdx, [r14+10h]
0x1800247fb  call    cs:__imp_DevObjGetClassDevs
0x180024801  test    eax, eax
0x180024803  jz      loc_180024940
0x180024809  xorps   xmm0, xmm0
0x18002480c  lea     r8, [rsp+0B8h+var_88]
0x180024811  movups  [rsp+0B8h+var_88], xmm0
0x180024816  xor     edx, edx
0x180024818  mov     dword ptr [rsp+0B8h+var_88], 30h ; '0'
0x180024820  mov     rcx, r15
0x180024823  movups  [rsp+0B8h+var_78], xmm0
0x180024828  movups  [rsp+0B8h+var_68], xmm0
0x18002482d  call    cs:__imp_DevObjEnumDeviceInfo
0x180024833  test    eax, eax
0x180024835  jz      loc_180024932
0x18002483b  add     rbx, 40h ; '@'
0x18002483f  add     rbx, r13
0x180024842  cmp     [rbx+18h], rdi
0x180024846  jb      short loc_180024863
0x180024848  cmp     qword ptr [rbx+18h], 7
0x18002484d  jbe     short loc_180024854
0x18002484f  mov     rcx, [rbx]
0x180024852  jmp     short loc_180024857
0x180024854  mov     rcx, rbx
0x180024857  mov     [rbx+10h], rdi
0x18002485b  mov     dword ptr [rcx], 31h ; '1'
0x180024861  jmp     short loc_180024875
0x180024863  lea     r9, a1; "1"
0x18002486a  mov     rdx, rdi
0x18002486d  mov     rcx, rbx
0x180024870  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180024875  mov     rax, [r14+10h]
0x180024879  cmp     rax, qword ptr cs:GUID_SensorType_AmbientLight.Data1
0x180024880  jnz     short loc_1800248CD
0x180024882  mov     rax, [r14+18h]
0x180024886  cmp     rax, qword ptr cs:GUID_SensorType_AmbientLight.Data4
0x18002488d  jnz     short loc_1800248CD
0x18002488f  call    ?IsColorCapable@CDeviceInterface@@AEAAHXZ; CDeviceInterface::IsColorCapable(void)
0x180024894  test    eax, eax
0x180024896  jz      short loc_1800248CD
0x180024898  cmp     [rbx+18h], rdi
0x18002489c  jb      short loc_1800248B9
0x18002489e  cmp     qword ptr [rbx+18h], 7
0x1800248a3  jbe     short loc_1800248AA
0x1800248a5  mov     rcx, [rbx]
0x1800248a8  jmp     short loc_1800248AD
0x1800248aa  mov     rcx, rbx
0x1800248ad  mov     [rbx+10h], rdi
0x1800248b1  mov     dword ptr [rcx], 32h ; '2'
0x1800248b7  jmp     short loc_180024932
0x1800248b9  lea     r9, a2; "2"
0x1800248c0  mov     rdx, rdi
0x1800248c3  mov     rcx, rbx
0x1800248c6  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800248cb  jmp     short loc_180024932
0x1800248cd  mov     rax, [r14+10h]
0x1800248d1  cmp     rax, qword ptr cs:GUID_SensorType_Proximity.Data1
0x1800248d8  jnz     short loc_180024932
0x1800248da  mov     rax, [r14+18h]
0x1800248de  cmp     rax, qword ptr cs:GUID_SensorType_Proximity.Data4
0x1800248e5  jnz     short loc_180024932
0x1800248e7  call    ?IsHumanPresenceCapable@CDeviceInterface@@AEAAHXZ; CDeviceInterface::IsHumanPresenceCapable(void)
0x1800248ec  test    eax, eax
0x1800248ee  jz      short loc_180024932
0x1800248f0  cmp     [rbx+18h], rdi
0x1800248f4  jb      short loc_180024911
0x1800248f6  cmp     qword ptr [rbx+18h], 7
0x1800248fb  jbe     short loc_180024902
0x1800248fd  mov     rcx, [rbx]
0x180024900  jmp     short loc_180024905
0x180024902  mov     rcx, rbx
0x180024905  mov     [rbx+10h], rdi
0x180024909  mov     dword ptr [rcx], 32h ; '2'
0x18002490f  jmp     short loc_180024923
0x180024911  lea     r9, a2; "2"
0x180024918  mov     rdx, rdi
0x18002491b  mov     rcx, rbx
0x18002491e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180024923  mov     rdx, r15; void *
0x180024926  call    ?GetPresenceCapabilities@CDeviceInterface@@AEAAIPEAX@Z; CDeviceInterface::GetPresenceCapabilities(void *)
0x18002492b  mov     [r13+650h], eax
0x180024932  mov     rcx, r15
0x180024935  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002493b  jmp     loc_180024A00
0x180024940  call    cs:__imp_GetLastError
0x180024946  mov     ebx, eax
0x180024948  test    eax, eax
0x18002494a  jle     short loc_180024955
0x18002494c  movzx   ebx, ax
0x18002494f  or      ebx, 80070000h
0x180024955  lea     r9, aDevobjcreatede_1; "DevObjCreateDeviceInfoList or DevObjGet"...
0x18002495c  mov     dword ptr [rsp+0B8h+var_98], ebx
0x180024960  mov     r8d, 7Dh ; '}'
0x180024966  mov     rdx, rsi
0x180024969  mov     ecx, ebp
0x18002496b  call    AslLogCallPrintf
0x180024970  cmp     cs:EnableDevInvStdErrLog, 0
0x180024977  jz      short loc_1800249C7
0x180024979  mov     ecx, ebp; Ix
0x18002497b  call    _o___acrt_iob_func_0
0x180024980  mov     rcx, rax; Stream
0x180024983  lea     rdx, Format; "Error: %s, %u: "
0x18002498a  mov     r9d, 7Dh ; '}'
0x180024990  mov     r8, rsi
0x180024993  call    fprintf
0x180024998  mov     ecx, ebp; Ix
0x18002499a  call    _o___acrt_iob_func_0
0x18002499f  mov     rcx, rax; Stream
0x1800249a2  lea     rdx, aDevobjcreatede_1; "DevObjCreateDeviceInfoList or DevObjGet"...
0x1800249a9  mov     r8d, ebx
0x1800249ac  call    fprintf
0x1800249b1  mov     ecx, ebp; Ix
0x1800249b3  call    _o___acrt_iob_func_0
0x1800249b8  mov     rcx, rax; Stream
0x1800249bb  lea     rdx, asc_18011EAD8; "\n"
0x1800249c2  call    fprintf
0x1800249c7  cmp     cs:g_DeviceMapLogFunction, 0
0x1800249cf  jz      short loc_1800249E5
0x1800249d1  mov     r8d, ebx
0x1800249d4  lea     rdx, aDevobjcreatede_1; "DevObjCreateDeviceInfoList or DevObjGet"...
0x1800249db  mov     ecx, 2000000h
0x1800249e0  call    TraceMessageCallback
0x1800249e5  lea     r9, aDevobjcreatede_1; "DevObjCreateDeviceInfoList or DevObjGet"...
0x1800249ec  mov     dword ptr [rsp+0B8h+var_98], ebx
0x1800249f0  mov     r8d, 7Dh ; '}'
0x1800249f6  mov     rdx, rsi
0x1800249f9  mov     ecx, edi
0x1800249fb  call    AslLogCallPrintf
0x180024a00  add     r12, rdi
0x180024a03  cmp     r12, 14h
0x180024a07  jnz     loc_1800247A7
0x180024a0d  mov     rdx, r13; struct IAmiInventoryItem *
0x180024a10  lea     rcx, ?g_DeviceInterfaceStore@@3VTelCacheProvider@@A; this
0x180024a17  call    ?AddItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::AddItem(IAmiInventoryItem *)
0x180024a1c  mov     ebx, eax
0x180024a1e  test    eax, eax
0x180024a20  jns     loc_180024AC4
0x180024a26  lea     r14, aTelcacheprovid_20; "TelCacheProvider::AddItem failed [%#x]"
0x180024a2d  mov     dword ptr [rsp+0B8h+var_98], eax
0x180024a31  lea     r15d, [r12+75h]
0x180024a36  mov     r9, r14
0x180024a39  mov     r8d, r15d
0x180024a3c  mov     rdx, rsi
0x180024a3f  mov     ecx, ebp
0x180024a41  call    AslLogCallPrintf
0x180024a46  cmp     cs:EnableDevInvStdErrLog, 0
0x180024a4d  jz      short loc_180024A96
0x180024a4f  mov     ecx, ebp; Ix
0x180024a51  call    _o___acrt_iob_func_0
0x180024a56  mov     rcx, rax; Stream
0x180024a59  lea     rdx, Format; "Error: %s, %u: "
0x180024a60  mov     r9d, r15d
0x180024a63  mov     r8, rsi
0x180024a66  call    fprintf
0x180024a6b  mov     ecx, ebp; Ix
0x180024a6d  call    _o___acrt_iob_func_0
0x180024a72  mov     rcx, rax; Stream
0x180024a75  mov     r8d, ebx
0x180024a78  mov     rdx, r14; Format
0x180024a7b  call    fprintf
0x180024a80  mov     ecx, ebp; Ix
0x180024a82  call    _o___acrt_iob_func_0
0x180024a87  mov     rcx, rax; Stream
0x180024a8a  lea     rdx, asc_18011EAD8; "\n"
0x180024a91  call    fprintf
0x180024a96  cmp     cs:g_DeviceMapLogFunction, 0
0x180024a9e  jz      short loc_180024AB0
0x180024aa0  mov     r8d, ebx
0x180024aa3  mov     rdx, r14
0x180024aa6  mov     ecx, 2000000h
0x180024aab  call    TraceMessageCallback
0x180024ab0  mov     r9, r14
0x180024ab3  mov     dword ptr [rsp+0B8h+var_98], ebx
0x180024ab7  mov     r8, r15
0x180024aba  mov     rdx, rsi
0x180024abd  mov     ecx, edi
0x180024abf  call    AslLogCallPrintf
0x180024ac4  xor     ebx, ebx
0x180024ac6  jmp     loc_180024B72
0x180024acb  lea     rdi, aTelcacheIsNotI; "Telcache is not initialized [%#x]"
0x180024ad2  mov     r14d, 4Dh ; 'M'
0x180024ad8  mov     ebx, 80004005h
0x180024add  mov     r9, rdi
0x180024ae0  mov     r8d, r14d
0x180024ae3  mov     dword ptr [rsp+0B8h+var_98], ebx
0x180024ae7  mov     rdx, rsi
0x180024aea  mov     ecx, ebp
0x180024aec  call    AslLogCallPrintf
0x180024af1  cmp     cs:EnableDevInvStdErrLog, 0
0x180024af8  jz      short loc_180024B41
0x180024afa  mov     ecx, ebp; Ix
0x180024afc  call    _o___acrt_iob_func_0
0x180024b01  mov     rcx, rax; Stream
0x180024b04  lea     rdx, Format; "Error: %s, %u: "
0x180024b0b  mov     r9d, r14d
0x180024b0e  mov     r8, rsi
0x180024b11  call    fprintf
0x180024b16  mov     ecx, ebp; Ix
0x180024b18  call    _o___acrt_iob_func_0
0x180024b1d  mov     rcx, rax; Stream
0x180024b20  mov     r8d, ebx
0x180024b23  mov     rdx, rdi; Format
0x180024b26  call    fprintf
0x180024b2b  mov     ecx, ebp; Ix
0x180024b2d  call    _o___acrt_iob_func_0
0x180024b32  mov     rcx, rax; Stream
0x180024b35  lea     rdx, asc_18011EAD8; "\n"
0x180024b3c  call    fprintf
0x180024b41  cmp     cs:g_DeviceMapLogFunction, 0
0x180024b49  jz      short loc_180024B5B
0x180024b4b  mov     r8d, ebx
0x180024b4e  mov     rdx, rdi
0x180024b51  mov     ecx, 2000000h
0x180024b56  call    TraceMessageCallback
0x180024b5b  mov     r9, rdi
0x180024b5e  mov     dword ptr [rsp+0B8h+var_98], ebx
0x180024b62  mov     r8, r14
0x180024b65  mov     rdx, rsi
0x180024b68  mov     ecx, 1
0x180024b6d  call    AslLogCallPrintf
0x180024b72  mov     eax, ebx
0x180024b74  mov     rcx, [rsp+0B8h+var_58]
0x180024b79  xor     rcx, rsp; StackCookie
0x180024b7c  call    __security_check_cookie
0x180024b81  add     rsp, 78h
0x180024b85  pop     r15
0x180024b87  pop     r14
0x180024b89  pop     r13
0x180024b8b  pop     r12
0x180024b8d  pop     rdi
0x180024b8e  pop     rsi
0x180024b8f  pop     rbp
0x180024b90  pop     rbx
0x180024b91  retn
```
