# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x1800258ac`
- end: `0x180025a1f`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$00@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$00@@6@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, const size_t **, const size_t **, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180037ac4`

## callees

- `0x1800258ac`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800259e6`
- `ntdll!EtwEventWriteTransfer` at `0x1800259e6`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const size_t **a7,
        const size_t **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  const size_t *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const size_t *v15; // rdx
  int v16; // ecx
  _DWORD v18[2]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v19; // [rsp+40h] [rbp-79h]
  __int16 *v20; // [rsp+50h] [rbp-69h] BYREF
  int v21; // [rsp+58h] [rbp-61h]
  int v22; // [rsp+5Ch] [rbp-5Dh]
  unsigned __int8 *v23; // [rsp+60h] [rbp-59h]
  int v24; // [rsp+68h] [rbp-51h]
  int v25; // [rsp+6Ch] [rbp-4Dh]
  __int64 v26; // [rsp+70h] [rbp-49h]
  __int64 v27; // [rsp+78h] [rbp-41h]
  __int64 v28; // [rsp+80h] [rbp-39h]
  __int64 v29; // [rsp+88h] [rbp-31h]
  const size_t *v30; // [rsp+90h] [rbp-29h]
  int v31; // [rsp+98h] [rbp-21h]
  int v32; // [rsp+9Ch] [rbp-1Dh]
  const size_t *v33; // [rsp+A0h] [rbp-19h]
  int v34; // [rsp+A8h] [rbp-11h]
  int v35; // [rsp+ACh] [rbp-Dh]
  __int64 v36; // [rsp+B0h] [rbp-9h]
  __int64 v37; // [rsp+B8h] [rbp-1h]
  __int64 v38; // [rsp+C0h] [rbp+7h]
  __int64 v39; // [rsp+C8h] [rbp+Fh]

  v38 = a10;
  v36 = a9;
  v11 = -1;
  v39 = 1;
  v37 = 1;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &pServiceName;
    v14 = 2;
  }
  v34 = v14;
  v33 = v12;
  v35 = 0;
  v15 = *a7;
  if ( *a7 )
  {
    do
      ++v11;
    while ( *((_WORD *)v15 + v11) );
    v16 = 2 * v11 + 2;
  }
  else
  {
    v15 = &pServiceName;
    v16 = 2;
  }
  v28 = a6;
  v26 = a5;
  v18[0] = *a2 << 24;
  v18[1] = *(unsigned __int16 *)(a2 + 1);
  v19 = *(_QWORD *)(a2 + 3);
  v20 = off_18009A050;
  v31 = v16;
  v30 = v15;
  v32 = 0;
  v29 = 8;
  v27 = 4;
  v21 = (unsigned __int16)*off_18009A050;
  v24 = *(unsigned __int16 *)(a2 + 11);
  v23 = a2 + 11;
  v22 = 2;
  v25 = 1;
  return EtwEventWriteTransfer(RegHandle, v18, 0, 0, 8, &v20);
}

```

## disassembly

```asm
0x1800258ac  push    rbp
0x1800258ae  lea     rbp, [rsp-27h]
0x1800258b3  sub     rsp, 0E0h
0x1800258ba  mov     rax, cs:__security_cookie
0x1800258c1  xor     rax, rsp
0x1800258c4  mov     [rbp+27h+var_10], rax
0x1800258c8  mov     rax, [rbp+27h+arg_48]
0x1800258cc  mov     r11d, 1
0x1800258d2  mov     [rbp+27h+var_20], rax
0x1800258d6  mov     r8, rdx
0x1800258d9  mov     rax, [rbp+27h+arg_40]
0x1800258dd  xor     r9d, r9d
0x1800258e0  mov     [rbp+27h+var_30], rax
0x1800258e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800258e8  mov     rax, [rbp+27h+arg_38]
0x1800258ec  lea     r10d, [r11+1]
0x1800258f0  mov     [rbp+27h+var_18], r11
0x1800258f4  mov     [rbp+27h+var_28], r11
0x1800258f8  mov     rdx, [rax]
0x1800258fb  test    rdx, rdx
0x1800258fe  jz      loc_180025A01
0x180025904  mov     rax, rcx
0x180025907  inc     rax
0x18002590a  cmp     [rdx+rax*2], r9w
0x18002590f  jnz     short loc_180025907
0x180025911  lea     eax, ds:2[rax*2]
0x180025918  mov     [rbp+27h+var_38], eax
0x18002591b  mov     rax, [rbp+27h+arg_30]
0x18002591f  mov     [rbp+27h+var_40], rdx
0x180025923  mov     [rbp+27h+var_34], r9d
0x180025927  mov     rdx, [rax]
0x18002592a  test    rdx, rdx
0x18002592d  jz      loc_180025A10
0x180025933  inc     rcx
0x180025936  cmp     [rdx+rcx*2], r9w
0x18002593b  jnz     short loc_180025933
0x18002593d  lea     ecx, ds:2[rcx*2]
0x180025944  mov     rax, [rbp+27h+arg_28]
0x180025948  mov     [rbp+27h+var_60], rax
0x18002594c  mov     rax, [rbp+27h+arg_20]
0x180025950  mov     [rbp+27h+var_70], rax
0x180025954  movzx   eax, byte ptr [r8]
0x180025958  shl     eax, 18h
0x18002595b  mov     [rsp+0E0h+var_A8], eax
0x18002595f  movzx   eax, word ptr [r8+1]
0x180025964  mov     [rbp+27h+var_A4], eax
0x180025967  mov     rax, [r8+3]
0x18002596b  mov     [rbp+27h+var_A0], rax
0x18002596f  mov     rax, cs:off_18009A050
0x180025976  mov     [rbp+27h+var_90], rax
0x18002597a  mov     [rbp+27h+var_48], ecx
0x18002597d  lea     rcx, [r8+0Bh]
0x180025981  mov     [rbp+27h+var_50], rdx
0x180025985  xor     r8d, r8d
0x180025988  mov     edx, 8
0x18002598d  mov     [rbp+27h+var_44], r9d
0x180025991  mov     [rbp+27h+var_58], rdx
0x180025995  mov     [rbp+27h+var_68], 4
0x18002599d  movzx   eax, word ptr [rax]
0x1800259a0  mov     [rbp+27h+var_88], eax
0x1800259a3  movzx   eax, word ptr [rcx]
0x1800259a6  mov     [rbp+27h+var_78], eax
0x1800259a9  lea     rax, _TraceLoggingMetadataEnd
0x1800259b0  mov     [rbp+27h+var_80], rcx
0x1800259b4  lea     rcx, _TraceLoggingMetadata
0x1800259bb  sub     eax, ecx
0x1800259bd  mov     [rbp+27h+var_84], r10d
0x1800259c1  mov     [rbp+27h+var_74], r11d
0x1800259c5  mov     [rsp+0E0h+var_B0], eax
0x1800259c9  mov     eax, [rsp+0E0h+var_B0]
0x1800259cd  mov     rcx, cs:RegHandle
0x1800259d4  lea     rax, [rbp+27h+var_90]
0x1800259d8  mov     [rsp+0E0h+var_B8], rax
0x1800259dd  mov     [rsp+0E0h+var_C0], edx
0x1800259e1  lea     rdx, [rsp+0E0h+var_A8]
0x1800259e6  call    cs:__imp_EtwEventWriteTransfer
0x1800259ec  mov     rcx, [rbp+27h+var_10]
0x1800259f0  xor     rcx, rsp; StackCookie
0x1800259f3  call    __security_check_cookie
0x1800259f8  add     rsp, 0E0h
0x1800259ff  pop     rbp
0x180025a00  retn
0x180025a01  lea     rdx, pServiceName
0x180025a08  mov     eax, r10d
0x180025a0b  jmp     loc_180025918
0x180025a10  lea     rdx, pServiceName
0x180025a17  mov     ecx, r10d
0x180025a1a  jmp     loc_180025944
```
