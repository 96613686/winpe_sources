# DllGetClassObject

- ea: `0x18002d134`
- end: `0x18002d2a0`
- name: `DllGetClassObject`
- size: `364`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180003070`
- `0x180003740`
- `0x18000a6a4`
- `0x180029330`
- `0x180029ae4`
- `0x18002a230`
- `0x18002b888`
- `0x18002d134`
- `0x180045020`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int (*ClassObjectFunction)(const struct _GUID *, const struct _GUID *, void **); // rdi
  _QWORD *v5; // rbx
  const IID *v6; // rsi
  int v8; // r15d
  __int64 v9; // r14
  _QWORD *v10; // rax
  __int64 v11; // rcx
  IID v12; // xmm0
  __int64 v13; // rax
  int UnmanagedCOMObject; // eax
  __int64 v15; // rcx
  HRESULT RealDll; // esi
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-18h] BYREF
  int v20; // [rsp+40h] [rbp-10h]
  HINSTANCE hModule; // [rsp+A8h] [rbp+58h] BYREF

  LODWORD(ClassObjectFunction) = 0;
  v5 = 0;
  v6 = riid;
  hModule = 0;
  v19 = 0;
  v8 = 1;
  v20 = 0;
  v9 = 0;
  v18 = 0;
  if ( g_pCVMList )
  {
    v10 = operator new(0x18u, (const struct NoThrow *)riid);
    v5 = v10;
    if ( v10 )
    {
      v12 = *rclsid;
      v10[2] = 0;
      v19 = v10;
      *(IID *)v10 = v12;
      v20 = 1;
      v13 = SORTEDARRAY<ClsVerMod>::FIND(v11, v10);
      v9 = v13;
      if ( v13 )
      {
        ClassObjectFunction = *(int (**)(const struct _GUID *, const struct _GUID *, void **))(v13 + 16);
        if ( ClassObjectFunction )
          goto LABEL_22;
      }
    }
    else
    {
      v5 = 0;
      v19 = 0;
    }
  }
  UnmanagedCOMObject = LoadUnmanagedCOMObject((struct _GUID *)rclsid, (__int64)&v18);
  RealDll = UnmanagedCOMObject;
  if ( UnmanagedCOMObject )
  {
    v8 = (int)ClassObjectFunction;
    if ( UnmanagedCOMObject < 0 || (RealDll = GetRealDll(&hModule, 1), RealDll < 0) )
    {
      ClassObjectFunction = (int (*)(const struct _GUID *, const struct _GUID *, void **))v18;
      goto LABEL_19;
    }
    ClassObjectFunction = GetDllGetClassObjectFunction(hModule);
    if ( !ClassObjectFunction )
    {
      RealDll = -2146232575;
      goto LABEL_19;
    }
  }
  else
  {
    ClassObjectFunction = (int (*)(const struct _GUID *, const struct _GUID *, void **))v18;
  }
  if ( !ClassObjectFunction )
    goto LABEL_23;
  if ( g_pCVMList )
  {
    if ( v9 )
    {
      *(_QWORD *)(v9 + 16) = ClassObjectFunction;
    }
    else if ( v5 )
    {
      v5[2] = ClassObjectFunction;
      v20 = 0;
      SORTEDARRAY<ClsVerMod>::PUSH(v15, v5);
    }
  }
LABEL_19:
  if ( ClassObjectFunction && !v8 )
  {
    v6 = riid;
LABEL_22:
    RealDll = ((__int64 (__fastcall *)(const IID *const, const IID *, LPVOID *))ClassObjectFunction)(rclsid, v6, ppv);
  }
LABEL_23:
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v19);
  return RealDll;
}

```

## disassembly

```asm
0x18002d134  mov     [rsp-38h+arg_0], rbx
0x18002d139  mov     [rsp-38h+arg_8], rdx
0x18002d13e  push    rbp
0x18002d13f  push    rsi
0x18002d140  push    rdi
0x18002d141  push    r12
0x18002d143  push    r13
0x18002d145  push    r14
0x18002d147  push    r15
0x18002d149  mov     rbp, rsp
0x18002d14c  sub     rsp, 50h
0x18002d150  xor     edi, edi
0x18002d152  mov     r13, r8
0x18002d155  cmp     cs:?g_pCVMList@@3PEAV?$SORTEDARRAY@VClsVerMod@@@@EA, rdi; SORTEDARRAY<ClsVerMod> * g_pCVMList
0x18002d15c  mov     ebx, edi
0x18002d15e  mov     rsi, rdx
0x18002d161  mov     [rbp+hModule], rdi
0x18002d165  mov     r12, rcx
0x18002d168  mov     [rbp+var_18], rbx
0x18002d16c  lea     r15d, [rdi+1]
0x18002d170  mov     [rbp+var_10], edi
0x18002d173  mov     r14d, edi
0x18002d176  mov     [rbp+var_20], rdi
0x18002d17a  jz      short loc_18002D1C2
0x18002d17c  lea     ecx, [rdi+18h]; unsigned __int64
0x18002d17f  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002d184  mov     rbx, rax
0x18002d187  test    rax, rax
0x18002d18a  jz      loc_18002D216
0x18002d190  movups  xmm0, xmmword ptr [r12]
0x18002d195  mov     rdx, rax
0x18002d198  mov     [rax+10h], rdi
0x18002d19c  mov     [rbp+var_18], rax
0x18002d1a0  movdqu  xmmword ptr [rax], xmm0
0x18002d1a4  mov     [rbp+var_10], r15d
0x18002d1a8  call    ?FIND@?$SORTEDARRAY@VClsVerMod@@@@QEAAPEAVClsVerMod@@PEAV2@@Z; SORTEDARRAY<ClsVerMod>::FIND(ClsVerMod *)
0x18002d1ad  mov     r14, rax
0x18002d1b0  test    rax, rax
0x18002d1b3  jz      short loc_18002D1C2
0x18002d1b5  mov     rdi, [rax+10h]
0x18002d1b9  test    rdi, rdi
0x18002d1bc  jnz     loc_18002D26A
0x18002d1c2  lea     rax, [rbp+var_20]
0x18002d1c6  mov     r9, r13
0x18002d1c9  lea     r8, [rbp+hModule]
0x18002d1cd  mov     [rsp+50h+var_30], rax; __int64
0x18002d1d2  mov     rdx, rsi
0x18002d1d5  mov     rcx, r12; struct _GUID *
0x18002d1d8  call    LoadUnmanagedCOMObject
0x18002d1dd  mov     esi, eax
0x18002d1df  test    eax, eax
0x18002d1e1  jnz     short loc_18002D21F
0x18002d1e3  mov     rdi, [rbp+var_20]
0x18002d1e7  test    rdi, rdi
0x18002d1ea  jz      loc_18002D27D
0x18002d1f0  cmp     cs:?g_pCVMList@@3PEAV?$SORTEDARRAY@VClsVerMod@@@@EA, 0; SORTEDARRAY<ClsVerMod> * g_pCVMList
0x18002d1f8  jz      short loc_18002D25C
0x18002d1fa  test    r14, r14
0x18002d1fd  jnz     short loc_18002D252
0x18002d1ff  test    rbx, rbx
0x18002d202  jz      short loc_18002D25C
0x18002d204  mov     rdx, rbx
0x18002d207  mov     [rbx+10h], rdi
0x18002d20b  mov     [rbp+var_10], r14d
0x18002d20f  call    ?PUSH@?$SORTEDARRAY@VClsVerMod@@@@QEAAXPEAVClsVerMod@@@Z; SORTEDARRAY<ClsVerMod>::PUSH(ClsVerMod *)
0x18002d214  jmp     short loc_18002D25C
0x18002d216  mov     rbx, rdi
0x18002d219  mov     [rbp+var_18], rbx
0x18002d21d  jmp     short loc_18002D1C2
0x18002d21f  mov     r15d, edi
0x18002d222  test    eax, eax
0x18002d224  js      short loc_18002D258
0x18002d226  mov     edx, 1; int
0x18002d22b  lea     rcx, [rbp+hModule]; HINSTANCE *
0x18002d22f  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x18002d234  mov     esi, eax
0x18002d236  test    eax, eax
0x18002d238  js      short loc_18002D258
0x18002d23a  mov     rcx, [rbp+hModule]; hModule
0x18002d23e  call    ?GetDllGetClassObjectFunction@@YAP6AJAEBU_GUID@@0PEAPEAX@ZPEAUHINSTANCE__@@@Z; GetDllGetClassObjectFunction(HINSTANCE__ *)
0x18002d243  mov     rdi, rax
0x18002d246  test    rax, rax
0x18002d249  jnz     short loc_18002D1E7
0x18002d24b  mov     esi, 80131701h
0x18002d250  jmp     short loc_18002D25C
0x18002d252  mov     [r14+10h], rdi
0x18002d256  jmp     short loc_18002D25C
0x18002d258  mov     rdi, [rbp+var_20]
0x18002d25c  test    rdi, rdi
0x18002d25f  jz      short loc_18002D27D
0x18002d261  test    r15d, r15d
0x18002d264  jnz     short loc_18002D27D
0x18002d266  mov     rsi, [rbp+arg_8]
0x18002d26a  mov     r8, r13
0x18002d26d  mov     rdx, rsi
0x18002d270  mov     rcx, r12
0x18002d273  mov     rax, rdi
0x18002d276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d27b  mov     esi, eax
0x18002d27d  lea     rcx, [rbp+var_18]
0x18002d281  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18002d286  mov     rbx, [rsp+50h+arg_0]
0x18002d28e  mov     eax, esi
0x18002d290  add     rsp, 50h
0x18002d294  pop     r15
0x18002d296  pop     r14
0x18002d298  pop     r13
0x18002d29a  pop     r12
0x18002d29c  pop     rdi
0x18002d29d  pop     rsi
0x18002d29e  pop     rbp
0x18002d29f  retn
```
