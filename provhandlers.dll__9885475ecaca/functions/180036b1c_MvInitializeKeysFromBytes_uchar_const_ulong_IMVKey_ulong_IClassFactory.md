# MvInitializeKeysFromBytes(uchar const *,ulong,IMVKey * * *,ulong *,IClassFactory *)

- ea: `0x180036b1c`
- end: `0x180036c76`
- name: `?MvInitializeKeysFromBytes@@YAJPEBEKPEAPEAPEAUIMVKey@@PEAKPEAUIClassFactory@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, struct IMVKey ***, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016a28`
- `0x18002a4f8`

## callees

- `0x1800076a4`
- `0x180015c3c`
- `0x180036710`
- `0x180036b1c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180036b75`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180036b75`

## string_xrefs

- `0x180036b89`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`

## pseudocode

```c
__int64 __fastcall MvInitializeKeysFromBytes(
        const unsigned __int8 *a1,
        unsigned int a2,
        struct IMVKey ***a3,
        unsigned int *a4)
{
  __int64 *v8; // rax
  HRESULT ClassObject; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // rcx
  __int64 result; // rax
  __int64 v14; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  __int128 v16; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v17[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v19; // [rsp+90h] [rbp+18h] BYREF
  __int64 v20; // [rsp+98h] [rbp+20h] BYREF

  *a3 = 0;
  *a4 = 0;
  v20 = 0;
  v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(&v20);
  ClassObject = CoGetClassObject(
                  &GUID_38be0989_9830_49a8_985b_7741219fd0fb,
                  1u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  (LPVOID *)v8);
  try
  {
    v10 = ClassObject;
    if ( ClassObject >= 0 )
    {
      v19 = 0;
      v16 = 0;
      v17[0] = &v16;
      v17[1] = &v20;
      v17[2] = &v19;
      MvVisitKeysFromBytes__lambda_06f2a676e6a644b54fec8940156dc900_(a1, a2, v17);
      *a3 = (struct IMVKey **)v16;
      *a4 = DWORD2(v16);
      *(_QWORD *)&v16 = 0;
      DWORD2(v16) = 0;
      v14 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
        (const char *)(unsigned int)ClassObject,
        ppv);
      v12 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      result = v10;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x116,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180036b1c  mov     rax, rsp
0x180036b1f  mov     [rax+8], rbx
0x180036b23  mov     [rax+10h], rsi
0x180036b27  push    rdi
0x180036b28  push    r14
0x180036b2a  push    r15
0x180036b2c  sub     rsp, 60h
0x180036b30  mov     rdi, r9
0x180036b33  mov     rsi, r8
0x180036b36  mov     r14d, edx
0x180036b39  mov     r15, rcx
0x180036b3c  mov     qword ptr [r8], 0
0x180036b43  mov     dword ptr [r9], 0
0x180036b4a  mov     qword ptr [rax+20h], 0
0x180036b52  lea     rcx, [rax+20h]
0x180036b56  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClassFactory>>)
0x180036b5b  mov     qword ptr [rsp+78h+ppv], rax; int
0x180036b60  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180036b67  xor     r8d, r8d; pvReserved
0x180036b6a  lea     edx, [r8+1]; dwClsContext
0x180036b6e  lea     rcx, _GUID_38be0989_9830_49a8_985b_7741219fd0fb; rclsid
0x180036b75  call    cs:__imp_CoGetClassObject
0x180036b7b  mov     ebx, eax
0x180036b7d  test    eax, eax
0x180036b7f  jns     short loc_180036BC8
0x180036b81  mov     rcx, [rsp+78h]; this
0x180036b86  mov     r9d, eax; char *
0x180036b89  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036b90  mov     edx, 0FCh; void *
0x180036b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b9a  nop
0x180036b9b  mov     rcx, [rsp+78h+arg_18]
0x180036ba3  test    rcx, rcx
0x180036ba6  jz      short loc_180036BC1
0x180036ba8  mov     [rsp+78h+arg_18], 0
0x180036bb4  mov     rax, [rcx]
0x180036bb7  mov     rax, [rax+10h]
0x180036bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bc0  nop
0x180036bc1  mov     eax, ebx
0x180036bc3  jmp     loc_180036C5F
0x180036bc8  mov     [rsp+78h+arg_10], 0
0x180036bd3  xorps   xmm0, xmm0
0x180036bd6  movups  [rsp+78h+var_48], xmm0
0x180036bdb  lea     rax, [rsp+78h+var_48]
0x180036be0  mov     [rsp+78h+var_38], rax
0x180036be5  lea     rax, [rsp+78h+arg_18]
0x180036bed  mov     [rsp+78h+var_30], rax
0x180036bf2  lea     rax, [rsp+78h+arg_10]
0x180036bfa  mov     [rsp+78h+var_28], rax
0x180036bff  lea     r8, [rsp+78h+var_38]
0x180036c04  mov     edx, r14d
0x180036c07  mov     rcx, r15
0x180036c0a  call    MvVisitKeysFromBytes__lambda_06f2a676e6a644b54fec8940156dc900___; MvVisitKeysFromBytes__lambda_06f2a676e6a644b54fec8940156dc900_
0x180036c0f  mov     rax, qword ptr [rsp+78h+var_48]
0x180036c14  mov     [rsi], rax
0x180036c17  mov     eax, dword ptr [rsp+78h+var_48+8]
0x180036c1b  mov     [rdi], eax
0x180036c1d  mov     qword ptr [rsp+78h+var_48], 0
0x180036c26  mov     dword ptr [rsp+78h+var_48+8], 0
0x180036c2e  mov     rcx, [rsp+78h+arg_18]
0x180036c36  test    rcx, rcx
0x180036c39  jz      short loc_180036C54
0x180036c3b  mov     [rsp+78h+arg_18], 0
0x180036c47  mov     rax, [rcx]
0x180036c4a  mov     rax, [rax+10h]
0x180036c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c53  nop
0x180036c54  xor     eax, eax
0x180036c56  jmp     short loc_180036C5F
0x180036c58  mov     eax, [rsp+78h+arg_10]
0x180036c5f  lea     r11, [rsp+78h+var_18]
0x180036c64  mov     rbx, [r11+20h]
0x180036c68  mov     rsi, [r11+28h]
0x180036c6c  mov     rsp, r11
0x180036c6f  pop     r15
0x180036c71  pop     r14
0x180036c73  pop     rdi
0x180036c74  retn
```
