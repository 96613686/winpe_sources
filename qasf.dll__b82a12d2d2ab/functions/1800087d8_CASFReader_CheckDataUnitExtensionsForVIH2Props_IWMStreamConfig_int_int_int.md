# CASFReader::CheckDataUnitExtensionsForVIH2Props(IWMStreamConfig *,int *,int *,int *)

- ea: `0x1800087d8`
- end: `0x18000896d`
- name: `?CheckDataUnitExtensionsForVIH2Props@CASFReader@@AEAAXPEAUIWMStreamConfig@@PEAH11@Z`
- size: `405`
- prototype: `void __fastcall(CASFReader *__hidden this, struct IWMStreamConfig *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ab04`

## callees

- `0x180001460`
- `0x1800087d8`
- `0x18001e5b9`
- `0x18001f010`

## pseudocode

```c
void __fastcall CASFReader::CheckDataUnitExtensionsForVIH2Props(
        CASFReader *this,
        struct IWMStreamConfig *a2,
        int *a3,
        int *a4,
        int *a5)
{
  struct IWMStreamConfigVtbl *lpVtbl; // rax
  unsigned __int16 i; // bx
  _WORD v9[2]; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 v10; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-20h] BYREF

  *a3 = 0;
  *a4 = 0;
  lpVtbl = a2->lpVtbl;
  v11 = 0;
  if ( ((__int64 (__fastcall *)(struct IWMStreamConfig *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &IID_IWMStreamConfig2,
         &v11) >= 0 )
  {
    v10 = 0;
    if ( (*(int (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v11 + 136LL))(v11, &v10) >= 0 )
    {
      for ( i = 0; i < v10; ++i )
      {
        v9[0] = 0;
        Buf2 = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v11 + 144LL))(
               v11,
               i,
               &Buf2,
               v9,
               0,
               0) >= 0 )
        {
          if ( !memcmp_0(&INSSBuffer3Prop_DShowAttributes, &Buf2, 0x10u) && v9[0] == 24 )
          {
            *a5 = 1;
          }
          else
          {
            if ( !memcmp_0(&WM_SampleExtensionGUID_PixelAspectRatio, &Buf2, 0x10u) && v9[0] == 2 )
              *a3 = 1;
            if ( !memcmp_0(&WM_SampleExtensionGUID_ContentType, &Buf2, 0x10u) && v9[0] == 1 )
              *a4 = 1;
          }
        }
      }
    }
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
}

```

## disassembly

```asm
0x1800087d8  mov     [rsp-28h+arg_0], rbx
0x1800087dd  push    rbp
0x1800087de  push    rsi
0x1800087df  push    r13
0x1800087e1  push    r14
0x1800087e3  push    r15
0x1800087e5  mov     rbp, rsp
0x1800087e8  sub     rsp, 70h
0x1800087ec  mov     rax, cs:__security_cookie
0x1800087f3  xor     rax, rsp
0x1800087f6  mov     [rbp+var_10], rax
0x1800087fa  mov     r15, [rbp+arg_20]
0x1800087fe  mov     r14, r8
0x180008801  mov     dword ptr [r8], 0
0x180008808  mov     rcx, rdx
0x18000880b  mov     dword ptr [r9], 0
0x180008812  lea     r8, [rbp+var_28]
0x180008816  mov     rax, [rdx]
0x180008819  mov     rsi, r9
0x18000881c  lea     rdx, IID_IWMStreamConfig2
0x180008823  mov     [rbp+var_28], 0
0x18000882b  mov     rax, [rax]
0x18000882e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008833  test    eax, eax
0x180008835  js      loc_180008937
0x18000883b  mov     rcx, [rbp+var_28]
0x18000883f  lea     rdx, [rbp+var_2C]
0x180008843  xor     eax, eax
0x180008845  mov     [rbp+var_2C], ax
0x180008849  mov     rax, [rcx]
0x18000884c  mov     rax, [rax+88h]
0x180008853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008858  test    eax, eax
0x18000885a  js      loc_180008937
0x180008860  xor     ebx, ebx
0x180008862  xor     eax, eax
0x180008864  cmp     ax, [rbp+var_2C]
0x180008868  jnb     loc_180008937
0x18000886e  lea     r13d, [rbx+1]
0x180008872  mov     rcx, [rbp+var_28]
0x180008876  lea     r9, [rbp+var_30]
0x18000887a  xor     eax, eax
0x18000887c  mov     [rsp+70h+var_48], 0
0x180008885  mov     [rbp+var_30], ax
0x180008889  lea     r8, [rbp+Buf2]
0x18000888d  xorps   xmm0, xmm0
0x180008890  mov     [rsp+70h+var_50], 0
0x180008899  movups  [rbp+Buf2], xmm0
0x18000889d  mov     rax, [rcx]
0x1800088a0  movzx   edx, bx
0x1800088a3  mov     rax, [rax+90h]
0x1800088aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088af  test    eax, eax
0x1800088b1  js      short loc_180008929
0x1800088b3  mov     r8d, 10h; Size
0x1800088b9  lea     rdx, [rbp+Buf2]; Buf2
0x1800088bd  lea     rcx, INSSBuffer3Prop_DShowAttributes; Buf1
0x1800088c4  call    memcmp_0
0x1800088c9  test    eax, eax
0x1800088cb  jnz     short loc_1800088DD
0x1800088cd  mov     eax, 18h
0x1800088d2  cmp     ax, [rbp+var_30]
0x1800088d6  jnz     short loc_1800088DD
0x1800088d8  mov     [r15], r13d
0x1800088db  jmp     short loc_180008929
0x1800088dd  mov     r8d, 10h; Size
0x1800088e3  lea     rdx, [rbp+Buf2]; Buf2
0x1800088e7  lea     rcx, WM_SampleExtensionGUID_PixelAspectRatio; Buf1
0x1800088ee  call    memcmp_0
0x1800088f3  test    eax, eax
0x1800088f5  jnz     short loc_180008905
0x1800088f7  mov     eax, 2
0x1800088fc  cmp     ax, [rbp+var_30]
0x180008900  jnz     short loc_180008905
0x180008902  mov     [r14], r13d
0x180008905  mov     r8d, 10h; Size
0x18000890b  lea     rdx, [rbp+Buf2]; Buf2
0x18000890f  lea     rcx, WM_SampleExtensionGUID_ContentType; Buf1
0x180008916  call    memcmp_0
0x18000891b  test    eax, eax
0x18000891d  jnz     short loc_180008929
0x18000891f  cmp     r13w, [rbp+var_30]
0x180008924  jnz     short loc_180008929
0x180008926  mov     [rsi], r13d
0x180008929  add     bx, r13w
0x18000892d  cmp     bx, [rbp+var_2C]
0x180008931  jb      loc_180008872
0x180008937  mov     rcx, [rbp+var_28]
0x18000893b  test    rcx, rcx
0x18000893e  jz      short loc_18000894C
0x180008940  mov     rax, [rcx]
0x180008943  mov     rax, [rax+10h]
0x180008947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000894c  mov     rcx, [rbp+var_10]
0x180008950  xor     rcx, rsp; StackCookie
0x180008953  call    __security_check_cookie
0x180008958  mov     rbx, [rsp+70h+arg_0]
0x180008960  add     rsp, 70h
0x180008964  pop     r15
0x180008966  pop     r14
0x180008968  pop     r13
0x18000896a  pop     rsi
0x18000896b  pop     rbp
0x18000896c  retn
```
