# CorBindToCurrentRuntime

- ea: `0x18002c1d0`
- end: `0x18002c352`
- name: `CorBindToCurrentRuntime`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1800239d0`

## callees

- `0x180008710`
- `0x180008bcc`
- `0x180029b38`
- `0x180029b70`
- `0x18002ba30`
- `0x18002c1d0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002c2b8`
- `KERNEL32!GetProcAddress` at `0x18002c2d9`
- `KERNEL32!GetProcAddress` at `0x18002c2b8`
- `KERNEL32!GetProcAddress` at `0x18002c2d9`
- `KERNEL32!GetLastError` at `0x18002c2c3`
- `KERNEL32!GetLastError` at `0x18002c2c3`

## string_xrefs

- `0x18002c2d2`: `DllGetClassObject`
- `0x18002c2b1`: `DllGetClassObjectInternal`

## pseudocode

```c
__int64 __fastcall CorBindToCurrentRuntime(CLRFullPath *a1, __int64 a2, __int64 a3, __int64 a4)
{
  RuntimeRequest *v7; // rcx
  int Installation; // ebx
  bool v9; // zf
  FARPROC ProcAddress; // rax
  HMODULE hModule; // [rsp+30h] [rbp-79h] BYREF
  int v13; // [rsp+38h] [rbp-71h] BYREF
  __int128 v14; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v15[2]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v16; // [rsp+60h] [rbp-49h]
  __int128 v17; // [rsp+70h] [rbp-39h]
  __int64 v18; // [rsp+80h] [rbp-29h]
  int v19; // [rsp+88h] [rbp-21h]
  __int64 v20; // [rsp+90h] [rbp-19h]
  int v21; // [rsp+98h] [rbp-11h]
  __int64 v22; // [rsp+A0h] [rbp-9h]
  __int64 v23; // [rsp+A8h] [rbp-1h]
  __int64 v24; // [rsp+B0h] [rbp+7h]
  int v25; // [rsp+B8h] [rbp+Fh]
  __int64 v26; // [rsp+C0h] [rbp+17h]

  v13 = 0;
  if ( CLRFullPath::GetFullPath(a1) )
    goto LABEL_5;
  v18 = 1;
  v14 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  v21 = 1;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = -1;
  Installation = RuntimeRequest::CopyString(v7, (const unsigned __int16 **)&v15[1], (const unsigned __int16 *)v7, 1);
  if ( Installation < 0 )
  {
    RuntimeRequest::~RuntimeRequest((RuntimeRequest *)&v14);
    return (unsigned int)Installation;
  }
  DWORD2(v17) = 1;
  Installation = RuntimeRequest::RequestRuntimeDll((RuntimeRequest *)&v14, 1, &v13);
  RuntimeRequest::~RuntimeRequest((RuntimeRequest *)&v14);
  v9 = Installation == 0;
  if ( Installation >= 0 )
  {
LABEL_5:
    hModule = 0;
    Installation = GetInstallation((CLRFullPath *)1, &hModule, 0);
    if ( Installation >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "DllGetClassObjectInternal");
      if ( !ProcAddress && (GetLastError() != 127 || (ProcAddress = GetProcAddress(hModule, "DllGetClassObject")) == 0) )
        return (unsigned int)-2146232575;
      hModule = 0;
      Installation = ((__int64 (__fastcall *)(__int64, GUID *, HMODULE *))ProcAddress)(a2, &IID_IClassFactory, &hModule);
      if ( Installation >= 0 )
      {
        Installation = (*(__int64 (__fastcall **)(HMODULE, _QWORD, __int64, __int64))(*(_QWORD *)hModule + 24LL))(
                         hModule,
                         0,
                         a3,
                         a4);
        (*(void (__fastcall **)(HMODULE))(*(_QWORD *)hModule + 16LL))(hModule);
      }
    }
    v9 = Installation == 0;
  }
  if ( v9 && !v13 )
    return 1;
  return (unsigned int)Installation;
}

```

## disassembly

```asm
0x18002c1d0  push    rbp
0x18002c1d2  push    rbx
0x18002c1d3  push    rsi
0x18002c1d4  push    rdi
0x18002c1d5  push    r12
0x18002c1d7  push    r14
0x18002c1d9  push    r15
0x18002c1db  lea     rbp, [rsp-27h]
0x18002c1e0  sub     rsp, 0D0h
0x18002c1e7  xor     r15d, r15d
0x18002c1ea  mov     rsi, r9
0x18002c1ed  mov     [rbp+57h+var_C8], r15d
0x18002c1f1  mov     r14, r8
0x18002c1f4  mov     rdi, rdx
0x18002c1f7  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18002c1fc  lea     r12d, [r15+1]
0x18002c200  test    rax, rax
0x18002c203  jnz     loc_18002C290
0x18002c209  xorps   xmm0, xmm0
0x18002c20c  mov     [rbp+57h+var_80], r12
0x18002c210  xorps   xmm1, xmm1
0x18002c213  movdqa  [rbp+57h+var_C0], xmm0
0x18002c218  mov     r9d, r12d; int
0x18002c21b  movdqa  xmmword ptr [rbp+57h+var_B0], xmm1
0x18002c220  mov     r8, rcx; unsigned __int16 *
0x18002c223  movdqa  [rbp+57h+var_A0], xmm0
0x18002c228  lea     rdx, [rbp+57h+var_B0+8]; unsigned __int16 **
0x18002c22c  mov     [rbp+57h+var_78], r15d
0x18002c230  movups  [rbp+57h+var_90], xmm1
0x18002c234  mov     [rbp+57h+var_70], r15
0x18002c238  mov     [rbp+57h+var_68], r12d
0x18002c23c  mov     [rbp+57h+var_60], r15
0x18002c240  mov     [rbp+57h+var_58], r15
0x18002c244  mov     [rbp+57h+var_50], r15
0x18002c248  mov     [rbp+57h+var_48], r15d
0x18002c24c  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x18002c254  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x18002c259  lea     rcx, [rbp+57h+var_C0]; this
0x18002c25d  mov     ebx, eax
0x18002c25f  test    eax, eax
0x18002c261  jns     short loc_18002C26D
0x18002c263  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002c268  jmp     loc_18002C33E
0x18002c26d  lea     r8, [rbp+57h+var_C8]; int *
0x18002c271  mov     dword ptr [rbp+57h+var_90+8], r12d
0x18002c275  mov     edx, r12d; int
0x18002c278  call    ?RequestRuntimeDll@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::RequestRuntimeDll(int,int *)
0x18002c27d  lea     rcx, [rbp+57h+var_C0]; this
0x18002c281  mov     ebx, eax
0x18002c283  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002c288  test    ebx, ebx
0x18002c28a  js      loc_18002C334
0x18002c290  xor     r8d, r8d; int
0x18002c293  mov     [rbp+57h+hModule], r15
0x18002c297  lea     rdx, [rbp+57h+hModule]; HINSTANCE *
0x18002c29b  mov     ecx, r12d; int
0x18002c29e  call    ?GetInstallation@@YAJHPEAPEAUHINSTANCE__@@H@Z; GetInstallation(int,HINSTANCE__ * *,int)
0x18002c2a3  mov     ebx, eax
0x18002c2a5  test    eax, eax
0x18002c2a7  js      loc_18002C332
0x18002c2ad  mov     rcx, [rbp+57h+hModule]; hModule
0x18002c2b1  lea     rdx, aDllgetclassobj_1; "DllGetClassObjectInternal"
0x18002c2b8  call    cs:__imp_GetProcAddress
0x18002c2be  test    rax, rax
0x18002c2c1  jnz     short loc_18002C2EB
0x18002c2c3  call    cs:__imp_GetLastError
0x18002c2c9  cmp     eax, 7Fh
0x18002c2cc  jnz     short loc_18002C2E4
0x18002c2ce  mov     rcx, [rbp+57h+hModule]; hModule
0x18002c2d2  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18002c2d9  call    cs:__imp_GetProcAddress
0x18002c2df  test    rax, rax
0x18002c2e2  jnz     short loc_18002C2EB
0x18002c2e4  mov     ebx, 80131701h
0x18002c2e9  jmp     short loc_18002C33E
0x18002c2eb  lea     r8, [rbp+57h+hModule]
0x18002c2ef  mov     [rbp+57h+hModule], r15
0x18002c2f3  lea     rdx, IID_IClassFactory
0x18002c2fa  mov     rcx, rdi
0x18002c2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c302  mov     ebx, eax
0x18002c304  test    eax, eax
0x18002c306  js      short loc_18002C332
0x18002c308  mov     rcx, [rbp+57h+hModule]
0x18002c30c  mov     r9, rsi
0x18002c30f  mov     r8, r14
0x18002c312  xor     edx, edx
0x18002c314  mov     rax, [rcx]
0x18002c317  mov     rax, [rax+18h]
0x18002c31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c320  mov     rcx, [rbp+57h+hModule]
0x18002c324  mov     ebx, eax
0x18002c326  mov     rax, [rcx]
0x18002c329  mov     rax, [rax+10h]
0x18002c32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c332  test    ebx, ebx
0x18002c334  jnz     short loc_18002C33E
0x18002c336  cmp     [rbp+57h+var_C8], r15d
0x18002c33a  cmovz   ebx, r12d
0x18002c33e  mov     eax, ebx
0x18002c340  add     rsp, 0D0h
0x18002c347  pop     r15
0x18002c349  pop     r14
0x18002c34b  pop     r12
0x18002c34d  pop     rdi
0x18002c34e  pop     rsi
0x18002c34f  pop     rbx
0x18002c350  pop     rbp
0x18002c351  retn
```
