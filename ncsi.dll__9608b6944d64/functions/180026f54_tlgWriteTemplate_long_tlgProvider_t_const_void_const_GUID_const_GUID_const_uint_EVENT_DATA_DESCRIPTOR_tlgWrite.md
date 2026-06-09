# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180026f54`
- end: `0x180027068`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const size_t **, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800299cc`

## callees

- `0x180026f54`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002703e`
- `ntdll!EtwEventWriteTransfer` at `0x18002703e`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const size_t **a5,
        __int64 a6,
        __int64 a7)
{
  const size_t *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _DWORD v11[2]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v12; // [rsp+40h] [rbp-31h]
  __int16 *v13; // [rsp+50h] [rbp-21h] BYREF
  int v14; // [rsp+58h] [rbp-19h]
  int v15; // [rsp+5Ch] [rbp-15h]
  unsigned __int8 *v16; // [rsp+60h] [rbp-11h]
  int v17; // [rsp+68h] [rbp-9h]
  int v18; // [rsp+6Ch] [rbp-5h]
  const size_t *v19; // [rsp+70h] [rbp-1h]
  int v20; // [rsp+78h] [rbp+7h]
  int v21; // [rsp+7Ch] [rbp+Bh]
  __int64 v22; // [rsp+80h] [rbp+Fh]
  __int64 v23; // [rsp+88h] [rbp+17h]
  __int64 v24; // [rsp+90h] [rbp+1Fh]
  __int64 v25; // [rsp+98h] [rbp+27h]

  v24 = a7;
  v22 = a6;
  v25 = 4;
  v23 = 8;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &pServiceName;
    v9 = 2;
  }
  v20 = v9;
  v11[0] = *a2 << 24;
  v11[1] = *(unsigned __int16 *)(a2 + 1);
  v12 = *(_QWORD *)(a2 + 3);
  v13 = off_18009A050;
  v19 = v7;
  v21 = 0;
  v14 = (unsigned __int16)*off_18009A050;
  v17 = *(unsigned __int16 *)(a2 + 11);
  v16 = a2 + 11;
  v15 = 2;
  v18 = 1;
  return EtwEventWriteTransfer(RegHandle, v11, 0, 0, 5, &v13);
}

```

## disassembly

```asm
0x180026f54  push    rbp
0x180026f56  lea     rbp, [rsp-3Fh]
0x180026f5b  sub     rsp, 0B0h
0x180026f62  mov     rax, cs:__security_cookie
0x180026f69  xor     rax, rsp
0x180026f6c  mov     [rbp+3Fh+var_10], rax
0x180026f70  mov     rax, [rbp+3Fh+arg_30]
0x180026f74  xor     r8d, r8d
0x180026f77  mov     [rbp+3Fh+var_20], rax
0x180026f7b  mov     rax, [rbp+3Fh+arg_28]
0x180026f7f  mov     [rbp+3Fh+var_30], rax
0x180026f83  mov     rax, [rbp+3Fh+arg_20]
0x180026f87  lea     r9d, [r8+2]
0x180026f8b  mov     [rbp+3Fh+var_18], 4
0x180026f93  mov     [rbp+3Fh+var_28], 8
0x180026f9b  mov     rcx, [rax]
0x180026f9e  test    rcx, rcx
0x180026fa1  jz      loc_180027059
0x180026fa7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026fab  inc     rax
0x180026fae  cmp     [rcx+rax*2], r8w
0x180026fb3  jnz     short loc_180026FAB
0x180026fb5  lea     eax, ds:2[rax*2]
0x180026fbc  mov     [rbp+3Fh+var_38], eax
0x180026fbf  movzx   eax, byte ptr [rdx]
0x180026fc2  shl     eax, 18h
0x180026fc5  mov     [rbp+3Fh+var_78], eax
0x180026fc8  movzx   eax, word ptr [rdx+1]
0x180026fcc  mov     [rbp+3Fh+var_74], eax
0x180026fcf  mov     rax, [rdx+3]
0x180026fd3  mov     [rbp+3Fh+var_70], rax
0x180026fd7  mov     rax, cs:off_18009A050
0x180026fde  mov     [rbp+3Fh+var_60], rax
0x180026fe2  mov     [rbp+3Fh+var_40], rcx
0x180026fe6  lea     rcx, [rdx+0Bh]
0x180026fea  mov     [rbp+3Fh+var_34], r8d
0x180026fee  lea     rdx, [rbp+3Fh+var_78]
0x180026ff2  movzx   eax, word ptr [rax]
0x180026ff5  mov     [rbp+3Fh+var_58], eax
0x180026ff8  movzx   eax, word ptr [rcx]
0x180026ffb  mov     [rbp+3Fh+var_48], eax
0x180026ffe  lea     rax, _TraceLoggingMetadataEnd
0x180027005  mov     [rbp+3Fh+var_50], rcx
0x180027009  lea     rcx, _TraceLoggingMetadata
0x180027010  sub     eax, ecx
0x180027012  mov     [rbp+3Fh+var_54], r9d
0x180027016  mov     [rbp+3Fh+var_44], 1
0x18002701d  xor     r9d, r9d
0x180027020  mov     [rbp+3Fh+var_80], eax
0x180027023  mov     eax, [rbp+3Fh+var_80]
0x180027026  mov     rcx, cs:RegHandle
0x18002702d  lea     rax, [rbp+3Fh+var_60]
0x180027031  mov     [rsp+0B0h+var_88], rax
0x180027036  mov     [rsp+0B0h+var_90], 5
0x18002703e  call    cs:__imp_EtwEventWriteTransfer
0x180027044  mov     rcx, [rbp+3Fh+var_10]
0x180027048  xor     rcx, rsp; StackCookie
0x18002704b  call    __security_check_cookie
0x180027050  add     rsp, 0B0h
0x180027057  pop     rbp
0x180027058  retn
0x180027059  lea     rcx, pServiceName
0x180027060  mov     eax, r9d
0x180027063  jmp     loc_180026FBC
```
