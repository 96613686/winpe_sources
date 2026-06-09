# WinMain

- ea: `0x14000f9f8`
- end: `0x14000fb61`
- name: `WinMain`
- size: `361`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f880`

## callees

- `0x14000ccfc`
- `0x14000f9f8`
- `0x140012320`
- `0x140027e30`
- `0x14002cc2c`
- `0x140031800`
- `0x1400318f8`

## import_xrefs

- `KERNEL32!SetDllDirectoryW` at `0x14000fa21`
- `KERNEL32!SetDllDirectoryW` at `0x14000fa21`
- `KERNEL32!HeapSetInformation` at `0x14000fa14`
- `KERNEL32!HeapSetInformation` at `0x14000fa14`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb43`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb4e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb43`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb4e`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  char *v6; // rcx
  unsigned __int16 *UnicodeCommandLine; // rax
  char *v8; // rcx
  __int64 *v9; // rbx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rax
  int v13; // eax
  __int64 v14; // rbx
  int v15; // edi
  __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  const unsigned __int16 *v20; // [rsp+20h] [rbp-48h]
  _BYTE v21[8]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+38h] [rbp-30h] BYREF
  BSTR bstrString[4]; // [rsp+48h] [rbp-20h]

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  SetDllDirectoryW(&WindowName);
  v22 = 0;
  *(_OWORD *)bstrString = 0;
  UnicodeCommandLine = util_GetUnicodeCommandLine(v6);
  util_InitActivityLogParamsW((struct ActivityLogParams *)&v22, hInstance, UnicodeCommandLine, nShowCmd, v20);
  CVsActivityLogSingletonSmartObject::CVsActivityLogSingletonSmartObject(
    (CVsActivityLogSingletonSmartObject *)v21,
    (struct ActivityLogParams *)&v22);
  v9 = &qword_14009DB70;
  if ( &qword_14009DB70 != (__int64 *)-1LL )
  {
    qword_14009D548 = (__int64)&qword_14009DB70;
    if ( qword_14009DB70 )
    {
      do
      {
        LOBYTE(v8) = 1;
        ((void (__fastcall *)(char *))v9[8])(v8);
        v9 += 9;
      }
      while ( *v9 );
    }
  }
  v10 = qword_14009D6A0;
  v11 = qword_14009D6A8;
  while ( v10 < v11 )
  {
    if ( *(_QWORD *)v10 )
    {
      LOBYTE(v8) = 1;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 56LL))(v8);
      v11 = qword_14009D6A8;
    }
    v10 += 8LL;
  }
  v12 = util_GetUnicodeCommandLine(v8);
  v13 = CDevEnvAppId::Run(v12, nShowCmd);
  v14 = qword_14009D548;
  v15 = v13;
  if ( qword_14009D548 )
  {
    while ( *(_QWORD *)v14 )
    {
      v16 = *(_QWORD *)(v14 + 32);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      *(_QWORD *)(v14 + 32) = 0;
      (*(void (__fastcall **)(_QWORD))(v14 + 64))(0);
      v14 += 72;
    }
  }
  v17 = qword_14009D6A0;
  v18 = qword_14009D6A8;
  while ( v17 < v18 )
  {
    if ( *(_QWORD *)v17 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 56LL))(0);
      v18 = qword_14009D6A8;
    }
    v17 += 8LL;
  }
  ATL::CAtlModule::Term((ATL::CAtlModule *)&Module);
  CVsActivityLogSingletonSmartObject::~CVsActivityLogSingletonSmartObject((CVsActivityLogSingletonSmartObject *)v21);
  SysFreeString(bstrString[1]);
  SysFreeString(bstrString[0]);
  return v15;
}

```

## disassembly

```asm
0x14000f9f8  mov     [rsp+arg_0], rbx
0x14000f9fd  push    rdi
0x14000f9fe  sub     rsp, 60h
0x14000fa02  mov     edi, r9d
0x14000fa05  mov     rbx, rcx
0x14000fa08  xor     r9d, r9d; HeapInformationLength
0x14000fa0b  xor     r8d, r8d; HeapInformation
0x14000fa0e  xor     ecx, ecx; HeapHandle
0x14000fa10  lea     edx, [r9+1]; HeapInformationClass
0x14000fa14  call    cs:__imp_HeapSetInformation
0x14000fa1a  lea     rcx, WindowName; lpPathName
0x14000fa21  call    cs:__imp_SetDllDirectoryW
0x14000fa27  xorps   xmm0, xmm0
0x14000fa2a  xorps   xmm1, xmm1
0x14000fa2d  movups  [rsp+68h+var_30], xmm0
0x14000fa32  movdqu  xmmword ptr [rsp+68h+bstrString], xmm1
0x14000fa38  call    ?util_GetUnicodeCommandLine@@YAPEAGPEAD@Z; util_GetUnicodeCommandLine(char *)
0x14000fa3d  mov     r8, rax; unsigned __int16 *
0x14000fa40  lea     rcx, [rsp+68h+var_30]; struct ActivityLogParams *
0x14000fa45  mov     r9d, edi; int
0x14000fa48  mov     rdx, rbx; HINSTANCE
0x14000fa4b  call    ?util_InitActivityLogParamsW@@YAJPEAUActivityLogParams@@PEAUHINSTANCE__@@PEAGHPEBG@Z; util_InitActivityLogParamsW(ActivityLogParams *,HINSTANCE__ *,ushort *,int,ushort const *)
0x14000fa50  lea     rdx, [rsp+68h+var_30]; struct ActivityLogParams *
0x14000fa55  lea     rcx, [rsp+68h+var_38]; this
0x14000fa5a  call    ??0CVsActivityLogSingletonSmartObject@@QEAA@PEAUActivityLogParams@@@Z; CVsActivityLogSingletonSmartObject::CVsActivityLogSingletonSmartObject(ActivityLogParams *)
0x14000fa5f  lea     rbx, qword_14009DB70
0x14000fa66  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000fa6a  jz      short loc_14000FA8C
0x14000fa6c  cmp     cs:qword_14009DB70, 0
0x14000fa74  mov     cs:qword_14009D548, rbx
0x14000fa7b  jz      short loc_14000FA8C
0x14000fa7d  mov     cl, 1
0x14000fa7f  call    qword ptr [rbx+40h]
0x14000fa82  lea     rbx, [rbx+48h]
0x14000fa86  cmp     qword ptr [rbx], 0
0x14000fa8a  jnz     short loc_14000FA7D
0x14000fa8c  mov     rbx, cs:qword_14009D6A0
0x14000fa93  mov     rax, cs:qword_14009D6A8
0x14000fa9a  jmp     short loc_14000FAB4
0x14000fa9c  mov     rdx, [rbx]
0x14000fa9f  test    rdx, rdx
0x14000faa2  jz      short loc_14000FAB0
0x14000faa4  mov     cl, 1
0x14000faa6  call    qword ptr [rdx+38h]
0x14000faa9  mov     rax, cs:qword_14009D6A8
0x14000fab0  add     rbx, 8
0x14000fab4  cmp     rbx, rax
0x14000fab7  jb      short loc_14000FA9C
0x14000fab9  call    ?util_GetUnicodeCommandLine@@YAPEAGPEAD@Z; util_GetUnicodeCommandLine(char *)
0x14000fabe  mov     rcx, rax; unsigned __int16 *
0x14000fac1  mov     edx, edi; int
0x14000fac3  call    ?Run@CDevEnvAppId@@SAHPEAGH@Z; CDevEnvAppId::Run(ushort *,int)
0x14000fac8  mov     rbx, cs:qword_14009D548
0x14000facf  mov     edi, eax
0x14000fad1  test    rbx, rbx
0x14000fad4  jz      short loc_14000FAFB
0x14000fad6  jmp     short loc_14000FAF5
0x14000fad8  mov     rcx, [rbx+20h]
0x14000fadc  test    rcx, rcx
0x14000fadf  jz      short loc_14000FAE7
0x14000fae1  mov     rax, [rcx]
0x14000fae4  call    qword ptr [rax+10h]
0x14000fae7  and     qword ptr [rbx+20h], 0
0x14000faec  xor     ecx, ecx
0x14000faee  call    qword ptr [rbx+40h]
0x14000faf1  add     rbx, 48h ; 'H'
0x14000faf5  cmp     qword ptr [rbx], 0
0x14000faf9  jnz     short loc_14000FAD8
0x14000fafb  mov     rbx, cs:qword_14009D6A0
0x14000fb02  mov     rax, cs:qword_14009D6A8
0x14000fb09  jmp     short loc_14000FB23
0x14000fb0b  mov     rdx, [rbx]
0x14000fb0e  test    rdx, rdx
0x14000fb11  jz      short loc_14000FB1F
0x14000fb13  xor     ecx, ecx
0x14000fb15  call    qword ptr [rdx+38h]
0x14000fb18  mov     rax, cs:qword_14009D6A8
0x14000fb1f  add     rbx, 8
0x14000fb23  cmp     rbx, rax
0x14000fb26  jb      short loc_14000FB0B
0x14000fb28  lea     rcx, _Module; this
0x14000fb2f  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000fb34  lea     rcx, [rsp+68h+var_38]; this
0x14000fb39  call    ??1CVsActivityLogSingletonSmartObject@@QEAA@XZ; CVsActivityLogSingletonSmartObject::~CVsActivityLogSingletonSmartObject(void)
0x14000fb3e  mov     rcx, [rsp+68h+bstrString+8]; bstrString
0x14000fb43  call    cs:__imp_SysFreeString
0x14000fb49  mov     rcx, [rsp+68h+bstrString]; bstrString
0x14000fb4e  call    cs:__imp_SysFreeString
0x14000fb54  mov     rbx, [rsp+68h+arg_0]
0x14000fb59  mov     eax, edi
0x14000fb5b  add     rsp, 60h
0x14000fb5f  pop     rdi
0x14000fb60  retn
```
