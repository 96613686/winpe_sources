# CWapDPUHelper::HasV2Node(IConfigManager2 *,ushort const *,int *)

- ea: `0x1800270b0`
- end: `0x1800271a1`
- name: `?HasV2Node@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGPEAH@Z`
- size: `241`
- prototype: `__int64 __fastcall(CWapDPUHelper *__hidden this, struct IConfigManager2 *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001488`
- `0x1800110bc`
- `0x1800270b0`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWapDPUHelper::HasV2Node(
        CWapDPUHelper *this,
        struct IConfigManager2 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v10; // [rsp+40h] [rbp-28h] BYREF
  const OLECHAR *v11; // [rsp+48h] [rbp-20h] BYREF
  const OLECHAR *v12; // [rsp+50h] [rbp-18h] BYREF
  int v13; // [rsp+78h] [rbp+10h] BYREF

  v10 = 0;
  if ( a2 && a3 && a4 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IConfigManager2 *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 80LL))(
           a2,
           a3,
           &v10);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 224LL))(v10, a4);
      if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147023728 )
      {
        v6 = 0;
        if ( (unsigned int)dword_18003E080 > 5 )
        {
          v11 = L"HasV2Node";
          v12 = a3;
          v13 = *a4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            0x80000000LL,
            (unsigned __int8 *)qword_180037878,
            v7,
            v8,
            (__int64)&v13,
            &v12,
            &v11);
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800270b0  mov     [rsp+arg_0], rbx
0x1800270b5  mov     [rsp+arg_10], rsi
0x1800270ba  push    rdi
0x1800270bb  sub     rsp, 60h
0x1800270bf  mov     rsi, r9
0x1800270c2  mov     rdi, r8
0x1800270c5  mov     r9, rdx
0x1800270c8  mov     [rsp+68h+var_28], 0
0x1800270d1  test    rdx, rdx
0x1800270d4  jnz     short loc_1800270E0
0x1800270d6  mov     ebx, 80070057h
0x1800270db  jmp     loc_180027182
0x1800270e0  test    rdi, rdi
0x1800270e3  jz      short loc_1800270D6
0x1800270e5  test    rsi, rsi
0x1800270e8  jz      short loc_1800270D6
0x1800270ea  mov     rax, [rdx]
0x1800270ed  lea     r8, [rsp+68h+var_28]
0x1800270f2  mov     rdx, rdi
0x1800270f5  mov     rcx, r9
0x1800270f8  mov     rax, [rax+50h]
0x1800270fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027101  mov     ebx, eax
0x180027103  test    eax, eax
0x180027105  js      short loc_180027182
0x180027107  mov     rcx, [rsp+68h+var_28]
0x18002710c  mov     rax, [rcx]
0x18002710f  mov     rdx, rsi
0x180027112  mov     rax, [rax+0E0h]
0x180027119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002711e  mov     ebx, eax
0x180027120  mov     ecx, 80000000h
0x180027125  add     eax, ecx
0x180027127  test    ecx, eax
0x180027129  jnz     short loc_180027133
0x18002712b  cmp     ebx, 80070490h
0x180027131  jnz     short loc_180027182
0x180027133  xor     ebx, ebx
0x180027135  mov     eax, cs:dword_18003E080
0x18002713b  cmp     eax, 5
0x18002713e  jbe     short loc_180027182
0x180027140  lea     rax, aHasv2node; "HasV2Node"
0x180027147  mov     [rsp+68h+var_20], rax
0x18002714c  mov     [rsp+68h+var_18], rdi
0x180027151  mov     eax, [rsi]
0x180027153  mov     [rsp+68h+arg_8], eax
0x180027157  lea     rax, [rsp+68h+var_20]
0x18002715c  mov     [rsp+68h+var_38], rax
0x180027161  lea     rax, [rsp+68h+var_18]
0x180027166  mov     [rsp+68h+var_40], rax
0x18002716b  lea     rax, [rsp+68h+arg_8]
0x180027170  mov     [rsp+68h+var_48], rax
0x180027175  lea     rdx, qword_180037878
0x18002717c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180027181  nop
0x180027182  lea     rcx, [rsp+68h+var_28]
0x180027187  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002718c  mov     eax, ebx
0x18002718e  lea     r11, [rsp+68h+var_8]
0x180027193  mov     rbx, [r11+10h]
0x180027197  mov     rsi, [r11+20h]
0x18002719b  mov     rsp, r11
0x18002719e  pop     rdi
0x18002719f  retn
```
