# DeploymentServiceCom::LoadTypeInfo(void)

- ea: `0x1800013cc`
- end: `0x1800014ac`
- name: `?LoadTypeInfo@DeploymentServiceCom@@QEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001220`
- `0x180001280`
- `0x180001300`
- `0x180001340`

## callees

- `0x1800013cc`
- `0x180012bd0`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001476`
- `KERNEL32!GetLastError` at `0x180001476`
- `KERNEL32!GetModuleFileNameW` at `0x180001416`
- `KERNEL32!GetModuleFileNameW` at `0x180001416`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000142e`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000142e`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::LoadTypeInfo(DeploymentServiceCom *this)
{
  _QWORD *v1; // rdi
  __int64 result; // rax
  DWORD ModuleFileNameW; // eax
  HRESULT v4; // ebx
  signed int LastError; // ecx
  ITypeLib *pptlib; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  pptlib = 0;
  v1 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
    return 0;
  ModuleFileNameW = GetModuleFileNameW(g_hModule, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    LastError = GetLastError();
    result = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
  }
  else
  {
    v4 = LoadTypeLib(Filename, &pptlib);
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
             pptlib,
             &IID_IDeploymentServiceCom,
             v1);
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v4 < 0 )
        *v1 = 0;
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800013cc  mov     [rsp+arg_8], rbx
0x1800013d1  push    rdi
0x1800013d2  sub     rsp, 250h
0x1800013d9  mov     rax, cs:__security_cookie
0x1800013e0  xor     rax, rsp
0x1800013e3  mov     [rsp+258h+var_18], rax
0x1800013eb  and     [rsp+258h+pptlib], 0
0x1800013f1  lea     rdi, [rcx+18h]
0x1800013f5  cmp     qword ptr [rdi], 0
0x1800013f9  jz      short loc_180001402
0x1800013fb  xor     eax, eax
0x1800013fd  jmp     loc_18000148B
0x180001402  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x180001409  lea     rdx, [rsp+258h+Filename]; lpFilename
0x18000140e  mov     ebx, 104h
0x180001413  mov     r8d, ebx; nSize
0x180001416  call    cs:__imp_GetModuleFileNameW
0x18000141c  test    eax, eax
0x18000141e  jz      short loc_180001476
0x180001420  cmp     eax, ebx
0x180001422  jz      short loc_180001476
0x180001424  lea     rdx, [rsp+258h+pptlib]; pptlib
0x180001429  lea     rcx, [rsp+258h+Filename]; szFile
0x18000142e  call    cs:__imp_LoadTypeLib
0x180001434  mov     ebx, eax
0x180001436  test    eax, eax
0x180001438  js      short loc_180001472
0x18000143a  mov     rcx, [rsp+258h+pptlib]
0x18000143f  lea     rdx, IID_IDeploymentServiceCom
0x180001446  mov     r8, rdi
0x180001449  mov     rax, [rcx]
0x18000144c  mov     rax, [rax+30h]
0x180001450  call    cs:__guard_dispatch_icall_fptr
0x180001456  mov     rcx, [rsp+258h+pptlib]
0x18000145b  mov     ebx, eax
0x18000145d  mov     rax, [rcx]
0x180001460  mov     rax, [rax+10h]
0x180001464  call    cs:__guard_dispatch_icall_fptr
0x18000146a  test    ebx, ebx
0x18000146c  jns     short loc_180001472
0x18000146e  and     qword ptr [rdi], 0
0x180001472  mov     eax, ebx
0x180001474  jmp     short loc_18000148B
0x180001476  call    cs:__imp_GetLastError
0x18000147c  mov     ecx, eax
0x18000147e  movzx   eax, ax
0x180001481  or      eax, 80070000h
0x180001486  test    ecx, ecx
0x180001488  cmovle  eax, ecx
0x18000148b  mov     rcx, [rsp+258h+var_18]
0x180001493  xor     rcx, rsp; StackCookie
0x180001496  call    __security_check_cookie
0x18000149b  mov     rbx, [rsp+258h+arg_8]
0x1800014a3  add     rsp, 250h
0x1800014aa  pop     rdi
0x1800014ab  retn
```
