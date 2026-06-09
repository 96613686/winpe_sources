# CPersistStreamInit::WriteIUNKNOWNColumnDataToStream(IUnknown * *,CRowInfo &,ushort)

- ea: `0x18001eb10`
- end: `0x18001ed54`
- name: `?WriteIUNKNOWNColumnDataToStream@CPersistStreamInit@@AEAAJPEAPEAUIUnknown@@AEAVCRowInfo@@G@Z`
- size: `580`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct IUnknown **, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001d350`

## callees

- `0x180002770`
- `0x180004384`
- `0x18001b558`
- `0x18001cd30`
- `0x18001eb10`
- `0x18002f0aa`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `msvcrt!_ismbblead` at `0x18001ec74`
- `msvcrt!_ismbblead` at `0x18001ec74`
- `KERNEL32!MultiByteToWideChar` at `0x18001ecc6`
- `KERNEL32!MultiByteToWideChar` at `0x18001ecc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistStreamInit::WriteIUNKNOWNColumnDataToStream(
        CPersistStreamInit *this,
        struct IUnknown **a2,
        struct CRowInfo *a3,
        unsigned __int16 a4)
{
  struct IUnknown *v5; // rsi
  int v6; // ebx
  unsigned __int16 Type; // r15
  unsigned __int16 v8; // r15
  CHAR v9; // di
  unsigned int v10; // r12d
  CHAR *p_MultiByteStr; // rdx
  unsigned int v12; // ecx
  int v13; // eax
  unsigned __int16 v14; // r9
  unsigned int v15; // r8d
  unsigned __int16 *v16; // rdx
  int v17; // r14d
  int v18; // ebx
  char v19; // al
  int v20; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown **v24; // [rsp+40h] [rbp-C0h]
  CHAR MultiByteStr; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[1023]; // [rsp+51h] [rbp-AFh] BYREF
  WCHAR WideCharStr[1024]; // [rsp+450h] [rbp+350h] BYREF

  v24 = a2;
  v5 = *a2;
  v23 = 0;
  v22 = 0;
  v6 = 0;
  Type = CMetaData::mdGetType(a3, a4);
  if ( v5 )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v5->lpVtbl->QueryInterface)(
           v5,
           &IID_ISequentialStream,
           &v23) >= 0 )
    {
      v8 = Type & 0xBFFF;
      memset_0(&MultiByteStr, 0, 0x400u);
      v9 = 0;
      do
      {
        if ( v9 )
          MultiByteStr = v9;
        v10 = 1024 - (v9 != 0);
        p_MultiByteStr = v26;
        if ( !v9 )
          p_MultiByteStr = &MultiByteStr;
        v6 = (*(__int64 (__fastcall **)(__int64, CHAR *, _QWORD, unsigned int *))(*(_QWORD *)v23 + 24LL))(
               v23,
               p_MultiByteStr,
               v10,
               &v22);
        if ( v6 < 0 )
          break;
        v12 = v22;
        if ( v22 > v10 )
        {
          v6 = -2147467259;
          break;
        }
        if ( v22 )
        {
          if ( v8 == 128 )
          {
            v13 = CPersistStreamInit::BinaryOut(this, (unsigned __int8 *)&MultiByteStr, v22);
          }
          else
          {
            if ( v8 == 130 )
            {
              v14 = 130;
              v15 = v22 >> 1;
              v16 = (unsigned __int16 *)&MultiByteStr;
            }
            else
            {
              v17 = v22 + (v9 != 0);
              if ( v22 == v10 )
              {
                v18 = 1023;
                do
                {
                  if ( !_ismbblead((unsigned __int8)v26[v18 - 1]) )
                    break;
                  --v18;
                }
                while ( v18 );
                v19 = v18 + 1;
                if ( !v18 )
                  v19 = 0;
                if ( (-v19 & 1) != 0 )
                {
                  --v17;
                  v9 = v26[1022];
                }
                else
                {
                  v9 = 0;
                }
              }
              v20 = MultiByteToWideChar(0, 0, &MultiByteStr, v17, WideCharStr, 1024);
              v14 = v8;
              v15 = v20;
              v16 = WideCharStr;
            }
            v13 = CPersistStreamInit::TextOutW(this, v16, v15, v14);
          }
          v6 = v13;
          if ( v13 < 0 )
            break;
          v12 = v22;
        }
      }
      while ( v12 >= v10 );
    }
    ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
    *v24 = 0;
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001eb10  mov     [rsp-8+arg_18], rbx
0x18001eb15  push    rbp
0x18001eb16  push    rsi
0x18001eb17  push    rdi
0x18001eb18  push    r12
0x18001eb1a  push    r13
0x18001eb1c  push    r14
0x18001eb1e  push    r15
0x18001eb20  lea     rbp, [rsp-0B60h]
0x18001eb28  sub     rsp, 0C60h
0x18001eb2f  mov     rax, cs:__security_cookie
0x18001eb36  xor     rax, rsp
0x18001eb39  mov     [rbp+0B90h+var_40], rax
0x18001eb40  mov     [rsp+0C90h+var_C50], rdx
0x18001eb45  mov     r13, rcx
0x18001eb48  mov     rsi, [rdx]
0x18001eb4b  mov     [rsp+0C90h+var_C58], 0
0x18001eb54  mov     [rsp+0C90h+var_C60], 0
0x18001eb5c  xor     ebx, ebx
0x18001eb5e  movzx   edx, r9w; unsigned __int16
0x18001eb62  mov     rcx, r8; this
0x18001eb65  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001eb6a  movzx   r15d, ax
0x18001eb6e  test    rsi, rsi
0x18001eb71  jz      loc_18001ED1D
0x18001eb77  mov     rax, [rsi]
0x18001eb7a  lea     r8, [rsp+0C90h+var_C58]
0x18001eb7f  lea     rdx, IID_ISequentialStream
0x18001eb86  mov     rcx, rsi
0x18001eb89  mov     rax, [rax]
0x18001eb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb91  test    eax, eax
0x18001eb93  js      loc_18001ED02
0x18001eb99  mov     eax, 0BFFFh
0x18001eb9e  and     r15w, ax
0x18001eba2  xor     edx, edx; Val
0x18001eba4  mov     r8d, 400h; Size
0x18001ebaa  lea     rcx, [rsp+0C90h+MultiByteStr]; void *
0x18001ebaf  call    memset_0
0x18001ebb4  xor     dil, dil
0x18001ebb7  test    dil, dil
0x18001ebba  jz      short loc_18001EBC1
0x18001ebbc  mov     [rsp+0C90h+MultiByteStr], dil
0x18001ebc1  xor     r14d, r14d
0x18001ebc4  test    dil, dil
0x18001ebc7  setnz   r14b
0x18001ebcb  mov     al, dil
0x18001ebce  neg     al
0x18001ebd0  sbb     r12d, r12d
0x18001ebd3  add     r12d, 400h
0x18001ebda  mov     rcx, [rsp+0C90h+var_C58]
0x18001ebdf  mov     rax, [rcx]
0x18001ebe2  lea     rdx, [rsp+0C90h+var_C3F]
0x18001ebe7  lea     r8, [rsp+0C90h+MultiByteStr]
0x18001ebec  test    dil, dil
0x18001ebef  cmovz   rdx, r8
0x18001ebf3  lea     r9, [rsp+0C90h+var_C60]
0x18001ebf8  mov     r8d, r12d
0x18001ebfb  mov     rax, [rax+18h]
0x18001ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec04  mov     ebx, eax
0x18001ec06  test    eax, eax
0x18001ec08  js      loc_18001ED02
0x18001ec0e  mov     ecx, [rsp+0C90h+var_C60]
0x18001ec12  cmp     ecx, r12d
0x18001ec15  ja      loc_18001ECFD
0x18001ec1b  test    ecx, ecx
0x18001ec1d  jz      loc_18001ECF2
0x18001ec23  mov     eax, 80h
0x18001ec28  cmp     r15w, ax
0x18001ec2c  jnz     short loc_18001EC43
0x18001ec2e  mov     r8d, ecx; unsigned int
0x18001ec31  lea     rdx, [rsp+0C90h+MultiByteStr]; unsigned __int8 *
0x18001ec36  mov     rcx, r13; this
0x18001ec39  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001ec3e  jmp     loc_18001ECE8
0x18001ec43  mov     eax, 82h
0x18001ec48  cmp     r15w, ax
0x18001ec4c  jnz     short loc_18001EC60
0x18001ec4e  mov     r9d, eax
0x18001ec51  shr     ecx, 1
0x18001ec53  mov     r8d, ecx
0x18001ec56  lea     rdx, [rsp+0C90h+MultiByteStr]
0x18001ec5b  jmp     loc_18001ECE0
0x18001ec60  add     r14d, ecx
0x18001ec63  cmp     ecx, r12d
0x18001ec66  jnz     short loc_18001ECA6
0x18001ec68  mov     ebx, 3FFh
0x18001ec6d  mov     eax, ebx
0x18001ec6f  movzx   ecx, [rsp+rax+0C90h+MultiByteStr]; Ch
0x18001ec74  call    cs:__imp__ismbblead
0x18001ec7b  nop     dword ptr [rax+rax+00h]
0x18001ec80  test    eax, eax
0x18001ec82  jz      short loc_18001EC89
0x18001ec84  add     ebx, 0FFFFFFFFh
0x18001ec87  jnz     short loc_18001EC6D
0x18001ec89  lea     eax, [rbx+1]
0x18001ec8c  test    ebx, ebx
0x18001ec8e  cmovz   eax, ebx
0x18001ec91  neg     eax
0x18001ec93  test    al, 1
0x18001ec95  jnz     short loc_18001EC9C
0x18001ec97  xor     dil, dil
0x18001ec9a  jmp     short loc_18001ECA6
0x18001ec9c  dec     r14d
0x18001ec9f  mov     dil, [rbp+0B90h+var_841]
0x18001eca6  mov     [rsp+0C90h+cchWideChar], 400h; cchWideChar
0x18001ecae  lea     rax, [rbp+0B90h+WideCharStr]
0x18001ecb5  mov     [rsp+0C90h+lpWideCharStr], rax; lpWideCharStr
0x18001ecba  mov     r9d, r14d; cbMultiByte
0x18001ecbd  lea     r8, [rsp+0C90h+MultiByteStr]; lpMultiByteStr
0x18001ecc2  xor     edx, edx; dwFlags
0x18001ecc4  xor     ecx, ecx; CodePage
0x18001ecc6  call    cs:__imp_MultiByteToWideChar
0x18001eccd  nop     dword ptr [rax+rax+00h]
0x18001ecd2  movzx   r9d, r15w; unsigned __int16
0x18001ecd6  mov     r8d, eax; unsigned int
0x18001ecd9  lea     rdx, [rbp+0B90h+WideCharStr]; unsigned __int16 *
0x18001ece0  mov     rcx, r13; this
0x18001ece3  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x18001ece8  mov     ebx, eax
0x18001ecea  test    eax, eax
0x18001ecec  js      short loc_18001ED02
0x18001ecee  mov     ecx, [rsp+0C90h+var_C60]
0x18001ecf2  cmp     ecx, r12d
0x18001ecf5  jnb     loc_18001EBB7
0x18001ecfb  jmp     short loc_18001ED02
0x18001ecfd  mov     ebx, 80004005h
0x18001ed02  mov     rax, [rsi]
0x18001ed05  mov     rcx, rsi
0x18001ed08  mov     rax, [rax+10h]
0x18001ed0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed11  mov     rax, [rsp+0C90h+var_C50]
0x18001ed16  mov     qword ptr [rax], 0
0x18001ed1d  lea     rcx, [rsp+0C90h+var_C58]
0x18001ed22  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001ed27  mov     eax, ebx
0x18001ed29  mov     rcx, [rbp+0B90h+var_40]
0x18001ed30  xor     rcx, rsp; StackCookie
0x18001ed33  call    __security_check_cookie
0x18001ed38  mov     rbx, [rsp+0C90h+arg_18]
0x18001ed40  add     rsp, 0C60h
0x18001ed47  pop     r15
0x18001ed49  pop     r14
0x18001ed4b  pop     r13
0x18001ed4d  pop     r12
0x18001ed4f  pop     rdi
0x18001ed50  pop     rsi
0x18001ed51  pop     rbp
0x18001ed52  retn
```
