# CPortClient::SendKernelSyncRequest(void *,unsigned __int64 *,DCOMPOSITION_DWM_LPC_EXTRA_DATA const *)

- ea: `0x18000aebc`
- end: `0x18000af3d`
- name: `?SendKernelSyncRequest@CPortClient@@QEAAJPEAXPEA_KPEBUDCOMPOSITION_DWM_LPC_EXTRA_DATA@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(CPortClient *__hidden this, void *, unsigned __int64 *, const struct DCOMPOSITION_DWM_LPC_EXTRA_DATA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002920`
- `0x18000b990`

## callees

- `0x18000352c`
- `0x18000aebc`
- `0x18000b25c`

## import_xrefs

- `win32u!NtDCompositionSendDwmLpcMessage` at `0x18000aee1`
- `win32u!NtDCompositionSendDwmLpcMessage` at `0x18000aee1`

## pseudocode

```c
__int64 __fastcall CPortClient::SendKernelSyncRequest(
        CPortClient *this,
        void *a2,
        unsigned __int64 *a3,
        const struct DCOMPOSITION_DWM_LPC_EXTRA_DATA *a4)
{
  unsigned int v6; // edi
  int v7; // r9d
  void *v9; // [rsp+28h] [rbp-10h]
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = *(_DWORD *)a3;
  v6 = NtDCompositionSendDwmLpcMessage(*((_QWORD *)this + 2), a2, &v10, a4) | 0x10000000;
  CPortClient::CheckHRESULT(this, v6);
  if ( v7 >= 0 )
  {
    v6 = 0;
    *a3 = v10;
  }
  else
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, v6, 0x22Fu, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18000aebc  mov     [rsp+arg_8], rbx
0x18000aec1  mov     [rsp+arg_10], rsi
0x18000aec6  push    rdi
0x18000aec7  sub     rsp, 30h
0x18000aecb  mov     eax, [r8]
0x18000aece  mov     rsi, r8
0x18000aed1  mov     rbx, rcx
0x18000aed4  mov     [rsp+38h+arg_0], eax
0x18000aed8  mov     rcx, [rcx+10h]
0x18000aedc  lea     r8, [rsp+38h+arg_0]
0x18000aee1  call    cs:__imp_NtDCompositionSendDwmLpcMessage
0x18000aee7  mov     edi, eax
0x18000aee9  mov     rcx, rbx; this
0x18000aeec  bts     edi, 1Ch
0x18000aef0  mov     r9d, eax
0x18000aef3  mov     edx, edi; int
0x18000aef5  call    ?CheckHRESULT@CPortClient@@AEAAJJ@Z; CPortClient::CheckHRESULT(long)
0x18000aefa  test    r9d, r9d
0x18000aefd  jns     short loc_18000AF22
0x18000aeff  mov     r8d, 9; unsigned int
0x18000af05  mov     [rsp+38h+var_18], 22Fh; unsigned int
0x18000af0d  mov     r9d, edi; int
0x18000af10  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x18000af17  lea     ecx, [r8-5]; unsigned int
0x18000af1b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000af20  jmp     short loc_18000AF2B
0x18000af22  mov     ecx, [rsp+38h+arg_0]
0x18000af26  xor     edi, edi
0x18000af28  mov     [rsi], rcx
0x18000af2b  mov     rbx, [rsp+38h+arg_8]
0x18000af30  mov     eax, edi
0x18000af32  mov     rsi, [rsp+38h+arg_10]
0x18000af37  add     rsp, 30h
0x18000af3b  pop     rdi
0x18000af3c  retn
```
