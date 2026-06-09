# GPMHelper::NotifyPerformanceMonitor(_tlgProvider_t const *,uint,_LUID)

- ea: `0x180008730`
- end: `0x1800088a5`
- name: `?NotifyPerformanceMonitor@GPMHelper@@QEAAXPEBU_tlgProvider_t@@IU_LUID@@@Z`
- size: `373`
- prototype: `void __fastcall(GPMHelper *__hidden this, const struct _tlgProvider_t *, unsigned int, struct _LUID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800088f0`

## callees

- `0x180008730`
- `0x180051c18`
- `0x180066b30`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180008797`
- `ntdll!RtlPublishWnfStateData` at `0x180008797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008772`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008772`

## pseudocode

```c
void __fastcall GPMHelper::NotifyPerformanceMonitor(
        GPMHelper *this,
        const struct _tlgProvider_t *a2,
        unsigned int a3,
        struct _LUID a4)
{
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // [rsp+80h] [rbp+7h] BYREF
  int v13; // [rsp+84h] [rbp+Bh] BYREF
  int v14; // [rsp+88h] [rbp+Fh] BYREF
  int v15; // [rsp+8Ch] [rbp+13h] BYREF
  int v16; // [rsp+90h] [rbp+17h] BYREF
  int v17; // [rsp+94h] [rbp+1Bh] BYREF
  int v18; // [rsp+98h] [rbp+1Fh] BYREF
  int v19; // [rsp+9Ch] [rbp+23h] BYREF
  int v20; // [rsp+A0h] [rbp+27h] BYREF
  struct _LUID v21; // [rsp+A8h] [rbp+2Fh] BYREF
  __int64 v22[4]; // [rsp+B0h] [rbp+37h] BYREF
  const struct _tlgProvider_t *v23; // [rsp+E8h] [rbp+6Fh] BYREF
  char v24; // [rsp+F0h] [rbp+77h] BYREF

  v23 = a2;
  if ( a3 == 10 || a3 == 1000 * (a3 / 0x3E8) )
  {
    LODWORD(v23) = GetCurrentProcessId();
    v8 = (unsigned int)RtlPublishWnfStateData(WNF_DX_GPM_TARGET, 0, &v23, 4, 0);
    if ( a3 == 10 && (unsigned int)dword_180108158 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180108158, 0x400000000000LL, v7, v8) )
      {
        v12 = *((_DWORD *)this + 6);
        v13 = *((_DWORD *)this + 4);
        v14 = *((_DWORD *)this + 3);
        v15 = *((_DWORD *)this + 2);
        v16 = *((_DWORD *)this + 1);
        v17 = *(_DWORD *)this;
        v18 = *((_DWORD *)this + 5);
        v21 = a4;
        v19 = v11;
        v24 = 2;
        v20 = 1;
        v22[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (unsigned int)byte_1800F17A1,
          v10,
          v11,
          (__int64)v22,
          (__int64)&v20,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&v21,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v13,
          (__int64)&v12);
      }
    }
  }
}

```

## disassembly

```asm
0x180008730  mov     [rsp-8+arg_0], rbx
0x180008735  mov     [rsp-8+arg_8], rdx
0x18000873a  push    rbp
0x18000873b  push    rsi
0x18000873c  push    rdi
0x18000873d  lea     rbp, [rsp-47h]
0x180008742  sub     rsp, 0C0h
0x180008749  mov     rbx, r9
0x18000874c  mov     edi, r8d
0x18000874f  mov     rsi, rcx
0x180008752  cmp     r8d, 0Ah
0x180008756  jz      short loc_180008772
0x180008758  mov     eax, 10624DD3h
0x18000875d  mul     edi
0x18000875f  shr     edx, 6
0x180008762  imul    r9d, edx, 3E8h
0x180008769  cmp     r8d, r9d
0x18000876c  jnz     loc_180008892
0x180008772  call    cs:__imp_GetCurrentProcessId
0x180008778  mov     rcx, cs:WNF_DX_GPM_TARGET
0x18000877f  lea     r8, [rbp+57h+arg_8]
0x180008783  mov     r9d, 4
0x180008789  mov     dword ptr [rbp+57h+arg_8], eax
0x18000878c  xor     edx, edx
0x18000878e  mov     [rsp+0D0h+var_B0], 0
0x180008797  call    cs:__imp_RtlPublishWnfStateData
0x18000879d  mov     r9d, eax
0x1800087a0  cmp     edi, 0Ah
0x1800087a3  jnz     loc_180008892
0x1800087a9  mov     ecx, cs:dword_180108158
0x1800087af  cmp     ecx, 5
0x1800087b2  jbe     loc_180008892
0x1800087b8  mov     rdx, 400000000000h
0x1800087c2  lea     rcx, dword_180108158
0x1800087c9  call    _tlgKeywordOn
0x1800087ce  test    al, al
0x1800087d0  jz      loc_180008892
0x1800087d6  mov     eax, [rsi+18h]
0x1800087d9  lea     rdx, byte_1800F17A1
0x1800087e0  mov     [rbp+57h+var_50], eax
0x1800087e3  mov     eax, [rsi+10h]
0x1800087e6  mov     [rbp+57h+var_4C], eax
0x1800087e9  mov     eax, [rsi+0Ch]
0x1800087ec  mov     [rbp+57h+var_48], eax
0x1800087ef  mov     eax, [rsi+8]
0x1800087f2  mov     [rbp+57h+var_44], eax
0x1800087f5  mov     eax, [rsi+4]
0x1800087f8  mov     [rbp+57h+var_40], eax
0x1800087fb  mov     eax, [rsi]
0x1800087fd  mov     [rbp+57h+var_3C], eax
0x180008800  mov     eax, [rsi+14h]
0x180008803  mov     [rbp+57h+var_38], eax
0x180008806  lea     rax, [rbp+57h+var_50]
0x18000880a  mov     [rsp+0D0h+var_58], rax
0x18000880f  lea     rax, [rbp+57h+var_4C]
0x180008813  mov     [rsp+0D0h+var_60], rax
0x180008818  lea     rax, [rbp+57h+var_48]
0x18000881c  mov     [rsp+0D0h+var_68], rax
0x180008821  lea     rax, [rbp+57h+var_44]
0x180008825  mov     [rsp+0D0h+var_70], rax
0x18000882a  lea     rax, [rbp+57h+var_40]
0x18000882e  mov     [rsp+0D0h+var_78], rax
0x180008833  lea     rax, [rbp+57h+var_3C]
0x180008837  mov     [rsp+0D0h+var_80], rax
0x18000883c  lea     rax, [rbp+57h+var_38]
0x180008840  mov     [rsp+0D0h+var_88], rax
0x180008845  lea     rax, [rbp+57h+var_28]
0x180008849  mov     [rsp+0D0h+var_90], rax
0x18000884e  lea     rax, [rbp+57h+var_34]
0x180008852  mov     [rsp+0D0h+var_98], rax
0x180008857  lea     rax, [rbp+57h+arg_10]
0x18000885b  mov     [rsp+0D0h+var_A0], rax
0x180008860  lea     rax, [rbp+57h+var_30]
0x180008864  mov     [rsp+0D0h+var_A8], rax
0x180008869  lea     rax, [rbp+57h+var_20]
0x18000886d  mov     [rsp+0D0h+var_B0], rax
0x180008872  mov     [rbp+57h+var_28], rbx
0x180008876  mov     [rbp+57h+var_34], r9d
0x18000887a  mov     [rbp+57h+arg_10], 2
0x18000887e  mov     [rbp+57h+var_30], 1
0x180008885  mov     [rbp+57h+var_20], 1000000h
0x18000888d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U2@U1@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@434444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008892  mov     rbx, [rsp+0D0h+arg_0]
0x18000889a  add     rsp, 0C0h
0x1800088a1  pop     rdi
0x1800088a2  pop     rsi
0x1800088a3  pop     rbp
0x1800088a4  retn
```
