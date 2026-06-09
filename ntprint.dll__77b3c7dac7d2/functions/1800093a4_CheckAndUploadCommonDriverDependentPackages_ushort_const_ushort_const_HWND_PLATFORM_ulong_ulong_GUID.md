# CheckAndUploadCommonDriverDependentPackages(ushort const *,ushort const *,HWND__ *,PLATFORM,ulong,ulong,_GUID *)

- ea: `0x1800093a4`
- end: `0x1800095aa`
- name: `?CheckAndUploadCommonDriverDependentPackages@@YAJPEBG0PEAUHWND__@@W4PLATFORM@@KKPEAU_GUID@@@Z`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b7ec`

## callees

- `0x1800093a4`
- `0x180009724`
- `0x180009a10`
- `0x180009b7c`
- `0x18000cc8c`
- `0x180012b28`
- `0x180020384`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000957c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000957c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009414`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009565`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009565`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180009467`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180009467`

## pseudocode

```c
__int64 __fastcall CheckAndUploadCommonDriverDependentPackages(
        const WCHAR *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        __int64 a7)
{
  int v7; // edi
  unsigned __int16 **v9; // rsi
  int v10; // ebx
  __int64 v11; // r14
  __int64 v12; // rdi
  unsigned __int16 *v13; // rcx
  int v15; // [rsp+40h] [rbp-48h] BYREF
  IID *rclsid; // [rsp+48h] [rbp-40h]

  v7 = 1;
  v15 = 1;
  if ( !a2 || !(unsigned int)ValidPlatform(a4) || !a6 || !a7 )
    return (unsigned int)-2147024809;
  v9 = (unsigned __int16 **)LocalAlloc(0x40u, 8 * a6);
  if ( !v9 )
    return (unsigned int)-2147024882;
  v10 = 0;
  v11 = 0;
  while ( (unsigned int)v11 < a6 )
  {
    rclsid = (IID *)(a7 + 16LL * (unsigned int)v11);
    if ( (unsigned int)IsInboxCorePrinterDriverGUID(rclsid) )
    {
      v9[v11] = 0;
    }
    else
    {
      v7 = 0;
      v15 = 0;
      v10 = StringFromIID(rclsid, &v9[v11]);
    }
    v11 = (unsigned int)(v11 + 1);
    if ( v10 < 0 )
      goto LABEL_25;
  }
  if ( !v7 )
  {
    v10 = CheckCommonDriversInInf(a2, a4, a6, v9, &v15);
    if ( v10 < 0 )
      goto LABEL_25;
    v7 = v15;
  }
  if ( v7 )
  {
LABEL_19:
    if ( !v7 )
    {
      v10 = CheckCommonDriversInDriverStore(a1, a3, a4, a5, a6, v9, &v15);
      if ( v10 >= 0 && !v15 )
      {
        if ( (a5 & 8) != 0 )
          v10 = -2147023728;
        else
          v10 = PromptForMissingCommonDriversAndUploadDriverIfFound(a1, a2, a3, a4, a6, v9);
      }
    }
    goto LABEL_25;
  }
  v10 = CheckCorePrinterDrivers(a1, a4, a6, v9, &v15);
  if ( v10 >= 0 )
  {
    v7 = v15;
    goto LABEL_19;
  }
LABEL_25:
  v12 = 0;
  do
  {
    v13 = v9[v12];
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v9[v12] = 0;
    }
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (unsigned int)v12 < a6 );
  LocalFree(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800093a4  mov     rax, rsp
0x1800093a7  mov     [rax+20h], rbx
0x1800093ab  mov     [rax+18h], r8
0x1800093af  mov     [rax+10h], rdx
0x1800093b3  mov     [rax+8], rcx
0x1800093b7  push    rbp
0x1800093b8  push    rsi
0x1800093b9  push    rdi
0x1800093ba  push    r12
0x1800093bc  push    r13
0x1800093be  push    r14
0x1800093c0  push    r15
0x1800093c2  sub     rsp, 50h
0x1800093c6  mov     edi, 1
0x1800093cb  mov     r15d, r9d
0x1800093ce  mov     [rax-48h], edi
0x1800093d1  test    rdx, rdx
0x1800093d4  jz      loc_18000958B
0x1800093da  mov     ecx, r9d
0x1800093dd  call    ValidPlatform
0x1800093e2  test    eax, eax
0x1800093e4  jz      loc_18000958B
0x1800093ea  mov     ebp, [rsp+88h+arg_28]
0x1800093f1  test    ebp, ebp
0x1800093f3  jz      loc_18000958B
0x1800093f9  mov     r12, [rsp+88h+arg_30]
0x180009401  test    r12, r12
0x180009404  jz      loc_18000958B
0x18000940a  lea     edx, ds:0[rbp*8]; uBytes
0x180009411  lea     ecx, [rdi+3Fh]; uFlags
0x180009414  call    cs:__imp_LocalAlloc
0x18000941a  mov     rsi, rax
0x18000941d  test    rax, rax
0x180009420  jz      loc_180009584
0x180009426  xor     ebx, ebx
0x180009428  xor     r14d, r14d
0x18000942b  cmp     r14d, ebp
0x18000942e  jnb     short loc_18000947B
0x180009430  mov     eax, r14d
0x180009433  lea     r13, [rsi+r14*8]
0x180009437  shl     rax, 4
0x18000943b  add     rax, r12
0x18000943e  mov     rcx, rax
0x180009441  mov     [rsp+88h+rclsid], rax
0x180009446  call    IsInboxCorePrinterDriverGUID
0x18000944b  test    eax, eax
0x18000944d  jz      short loc_180009459
0x18000944f  mov     qword ptr [r13+0], 0
0x180009457  jmp     short loc_18000946F
0x180009459  mov     rcx, [rsp+88h+rclsid]; rclsid
0x18000945e  xor     edi, edi
0x180009460  mov     rdx, r13; lplpsz
0x180009463  mov     [rsp+88h+var_48], edi
0x180009467  call    cs:__imp_StringFromIID
0x18000946d  mov     ebx, eax
0x18000946f  inc     r14d
0x180009472  test    ebx, ebx
0x180009474  jns     short loc_18000942B
0x180009476  jmp     loc_180009551
0x18000947b  mov     r13, [rsp+88h+arg_8]
0x180009483  test    edi, edi
0x180009485  jnz     short loc_1800094B0
0x180009487  lea     rax, [rsp+88h+var_48]
0x18000948c  mov     r9, rsi
0x18000948f  mov     r8d, ebp
0x180009492  mov     [rsp+88h+var_68], rax
0x180009497  mov     edx, r15d
0x18000949a  mov     rcx, r13
0x18000949d  call    ?CheckCommonDriversInInf@@YAJPEBGW4PLATFORM@@KPEAPEAGPEAH@Z; CheckCommonDriversInInf(ushort const *,PLATFORM,ulong,ushort * *,int *)
0x1800094a2  mov     ebx, eax
0x1800094a4  test    eax, eax
0x1800094a6  js      loc_180009551
0x1800094ac  mov     edi, [rsp+88h+var_48]
0x1800094b0  mov     r14, [rsp+88h+arg_0]
0x1800094b8  test    edi, edi
0x1800094ba  jnz     short loc_1800094E1
0x1800094bc  lea     rax, [rsp+88h+var_48]
0x1800094c1  mov     r9, rsi
0x1800094c4  mov     r8d, ebp
0x1800094c7  mov     [rsp+88h+var_68], rax
0x1800094cc  mov     edx, r15d
0x1800094cf  mov     rcx, r14
0x1800094d2  call    ?CheckCorePrinterDrivers@@YAJPEBGW4PLATFORM@@KPEAPEAGPEAH@Z; CheckCorePrinterDrivers(ushort const *,PLATFORM,ulong,ushort * *,int *)
0x1800094d7  mov     ebx, eax
0x1800094d9  test    eax, eax
0x1800094db  js      short loc_180009551
0x1800094dd  mov     edi, [rsp+88h+var_48]
0x1800094e1  mov     r12, [rsp+88h+arg_10]
0x1800094e9  test    edi, edi
0x1800094eb  jnz     short loc_180009551
0x1800094ed  mov     r9d, [rsp+88h+arg_20]
0x1800094f5  lea     rax, [rsp+88h+var_48]
0x1800094fa  mov     [rsp+88h+var_58], rax
0x1800094ff  mov     r8d, r15d
0x180009502  mov     [rsp+88h+var_60], rsi
0x180009507  mov     rdx, r12
0x18000950a  mov     rcx, r14
0x18000950d  mov     dword ptr [rsp+88h+var_68], ebp
0x180009511  call    ?CheckCommonDriversInDriverStore@@YAJPEBGPEAUHWND__@@W4PLATFORM@@KKPEAPEAGPEAH@Z; CheckCommonDriversInDriverStore(ushort const *,HWND__ *,PLATFORM,ulong,ulong,ushort * *,int *)
0x180009516  mov     ebx, eax
0x180009518  test    eax, eax
0x18000951a  js      short loc_180009551
0x18000951c  mov     edi, [rsp+88h+var_48]
0x180009520  test    edi, edi
0x180009522  jnz     short loc_180009551
0x180009524  test    byte ptr [rsp+88h+arg_20], 8
0x18000952c  jnz     short loc_18000954C
0x18000952e  mov     [rsp+88h+var_60], rsi
0x180009533  mov     r9d, r15d
0x180009536  mov     r8, r12
0x180009539  mov     dword ptr [rsp+88h+var_68], ebp
0x18000953d  mov     rdx, r13
0x180009540  mov     rcx, r14
0x180009543  call    ?PromptForMissingCommonDriversAndUploadDriverIfFound@@YAJPEBG0PEAUHWND__@@W4PLATFORM@@KPEAPEAG@Z; PromptForMissingCommonDriversAndUploadDriverIfFound(ushort const *,ushort const *,HWND__ *,PLATFORM,ulong,ushort * *)
0x180009548  mov     ebx, eax
0x18000954a  jmp     short loc_180009551
0x18000954c  mov     ebx, 80070490h
0x180009551  test    rsi, rsi
0x180009554  jz      short loc_180009590
0x180009556  xor     edi, edi
0x180009558  test    ebp, ebp
0x18000955a  jz      short loc_180009579
0x18000955c  mov     rcx, [rsi+rdi*8]; pv
0x180009560  test    rcx, rcx
0x180009563  jz      short loc_180009573
0x180009565  call    cs:__imp_CoTaskMemFree
0x18000956b  mov     qword ptr [rsi+rdi*8], 0
0x180009573  inc     edi
0x180009575  cmp     edi, ebp
0x180009577  jb      short loc_18000955C
0x180009579  mov     rcx, rsi; hMem
0x18000957c  call    cs:__imp_LocalFree
0x180009582  jmp     short loc_180009590
0x180009584  mov     ebx, 8007000Eh
0x180009589  jmp     short loc_180009590
0x18000958b  mov     ebx, 80070057h
0x180009590  mov     eax, ebx
0x180009592  mov     rbx, [rsp+88h+arg_18]
0x18000959a  add     rsp, 50h
0x18000959e  pop     r15
0x1800095a0  pop     r14
0x1800095a2  pop     r13
0x1800095a4  pop     r12
0x1800095a6  pop     rdi
0x1800095a7  pop     rsi
0x1800095a8  pop     rbp
0x1800095a9  retn
```
