# NotifyDDMForRoutingDomainChange(_GUID *,ulong,void *)

- ea: `0x1800161b8`
- end: `0x1800162cc`
- name: `?NotifyDDMForRoutingDomainChange@@YAKPEAU_GUID@@KPEAX@Z`
- size: `276`
- prototype: `unsigned int __fastcall(struct _GUID *, unsigned int, void *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003258`
- `0x18000eb60`
- `0x18001382c`
- `0x180014244`
- `0x180014fcc`

## callees

- `0x18000df70`
- `0x1800161b8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `MPRDDM!DDMHandleRoutingDomainConfigChange` at `0x18001623b`
- `MPRDDM!DDMHandleRoutingDomainConfigChange` at `0x18001623b`

## string_xrefs

- `0x180016252`: `NotifyDDMForRoutingDomainChange: DDMHandleRoutingDomainConfigChange failed:%d.`

## pseudocode

```c
__int64 __fastcall NotifyDDMForRoutingDomainChange(struct _GUID *a1, unsigned int a2, void *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int128 *v8; // r9
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+54h] [rbp-ACh]
  __int128 v14; // [rsp+64h] [rbp-9Ch]
  int v15; // [rsp+74h] [rbp-8Ch]
  int v16; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v16 = 0;
  v6 = 0;
  memset_0(v17, 0, sizeof(v17));
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v11 = 0;
  if ( (gbldwDIMComponentsLoaded & 4) != 0 )
  {
    v10 = (__int128)*a1;
    v7 = DDMHandleRoutingDomainConfigChange(a2, &v10, a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v16) = 0;
        LOWORD(v12) = 0;
        FormatRRASErrorString(
          &v16,
          L"NotifyDDMForRoutingDomainChange: DDMHandleRoutingDomainConfigChange failed:%d.",
          v7);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v8 = &v11;
          if ( a1 )
            LODWORD(v8) = (_DWORD)a1;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v16,
            (_DWORD)v8,
            0,
            (__int64)&v12);
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800161b8  push    rbp
0x1800161ba  push    rbx
0x1800161bb  push    rsi
0x1800161bc  push    rdi
0x1800161bd  push    r14
0x1800161bf  lea     rbp, [rsp-790h]
0x1800161c7  sub     rsp, 890h
0x1800161ce  mov     rax, cs:__security_cookie
0x1800161d5  xor     rax, rsp
0x1800161d8  mov     [rbp+7B0h+var_30], rax
0x1800161df  mov     r14, r8
0x1800161e2  mov     esi, edx
0x1800161e4  mov     rdi, rcx
0x1800161e7  xor     eax, eax
0x1800161e9  xor     edx, edx; Val
0x1800161eb  mov     [rbp+7B0h+var_830], eax
0x1800161ee  mov     r8d, 7FCh; Size
0x1800161f4  lea     rcx, [rbp+7B0h+var_82C]; void *
0x1800161f8  xor     ebx, ebx
0x1800161fa  call    memset_0
0x1800161ff  xor     eax, eax
0x180016201  xorps   xmm0, xmm0
0x180016204  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18001620b  mov     [rsp+8B0h+var_860], eax
0x18001620f  movups  [rsp+8B0h+var_85C], xmm0
0x180016214  mov     [rsp+8B0h+var_83C], eax
0x180016218  movups  [rsp+8B0h+var_84C], xmm0
0x18001621d  movups  [rsp+8B0h+var_870], xmm0
0x180016222  jz      loc_1800162AD
0x180016228  movups  xmm0, xmmword ptr [rdi]
0x18001622b  mov     r8, r14
0x18001622e  lea     rdx, [rsp+8B0h+var_880]
0x180016233  mov     ecx, esi
0x180016235  movdqu  [rsp+8B0h+var_880], xmm0
0x18001623b  call    cs:__imp_DDMHandleRoutingDomainConfigChange
0x180016241  mov     ebx, eax
0x180016243  test    eax, eax
0x180016245  jz      short loc_1800162AD
0x180016247  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001624e  jz      short loc_1800162AD
0x180016250  xor     ecx, ecx
0x180016252  lea     rdx, aNotifyddmforro; "NotifyDDMForRoutingDomainChange: DDMHan"...
0x180016259  mov     word ptr [rbp+7B0h+var_830], cx
0x18001625d  mov     r8d, eax
0x180016260  mov     word ptr [rsp+8B0h+var_860], cx
0x180016265  lea     rcx, [rbp+7B0h+var_830]
0x180016269  call    FormatRRASErrorString
0x18001626e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016275  jz      short loc_1800162AD
0x180016277  test    rdi, rdi
0x18001627a  lea     rax, [rsp+8B0h+var_860]
0x18001627f  mov     [rsp+8B0h+var_888], rax
0x180016284  lea     r9, [rsp+8B0h+var_870]
0x180016289  cmovnz  r9, rdi
0x18001628d  mov     [rsp+8B0h+var_890], 0
0x180016296  lea     r8, [rbp+7B0h+var_830]
0x18001629a  lea     rdx, RasDimParamTraceError
0x1800162a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800162a8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800162ad  mov     eax, ebx
0x1800162af  mov     rcx, [rbp+7B0h+var_30]
0x1800162b6  xor     rcx, rsp; StackCookie
0x1800162b9  call    __security_check_cookie
0x1800162be  add     rsp, 890h
0x1800162c5  pop     r14
0x1800162c7  pop     rdi
0x1800162c8  pop     rsi
0x1800162c9  pop     rbx
0x1800162ca  pop     rbp
0x1800162cb  retn
```
