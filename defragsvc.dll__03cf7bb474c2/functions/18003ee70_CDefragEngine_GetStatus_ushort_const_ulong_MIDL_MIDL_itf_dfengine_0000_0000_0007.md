# CDefragEngine::GetStatus(ushort const *,ulong *,__MIDL___MIDL_itf_dfengine_0000_0000_0007 * *)

- ea: `0x18003ee70`
- end: `0x18003eff7`
- name: `?GetStatus@CDefragEngine@@UEAAJPEBGPEAKPEAPEAU__MIDL___MIDL_itf_dfengine_0000_0000_0007@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(CDefragEngine *__hidden this, const unsigned __int16 *Src, unsigned int *, struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001d914`
- `0x18001df64`
- `0x18003ee70`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ef35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ef35`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDefragEngine::GetStatus(
        struct CDfVolumeList **this,
        const unsigned __int16 *Src,
        unsigned int *a3,
        struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 **a4)
{
  unsigned int v8; // esi
  __int16 v9; // ax
  int VolumeAsyncFromPath; // ebx
  struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *v11; // rdi
  struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *v13; // [rsp+20h] [rbp-40h] BYREF
  int v14; // [rsp+28h] [rbp-38h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-34h]
  __int16 v16; // [rsp+2Eh] [rbp-32h]
  unsigned int v17; // [rsp+A0h] [rbp+40h] BYREF
  struct IDefragAsyncWorker *v18; // [rsp+A8h] [rbp+48h] BYREF

  v8 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CDefragEngine::GetStatus", 1321, 1);
  v18 = 0;
  v13 = 0;
  v17 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = 1328;
  if ( !a3 || (*a3 = 0, v15 = 1328, v9 = 1329, !a4) )
  {
    VolumeAsyncFromPath = -2147024809;
    goto LABEL_15;
  }
  v14 = 0;
  v15 = 1329;
  if ( Src )
  {
    VolumeAsyncFromPath = CDefragEngine::_GetVolumeAsyncFromPath(this, Src, &v18, 0);
    v14 = VolumeAsyncFromPath;
    v9 = 1334;
    if ( VolumeAsyncFromPath >= 0 )
    {
      v15 = 1334;
      v11 = (struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *)CoTaskMemAlloc(0xD0u);
      v9 = 1338;
      if ( !v11 )
      {
        VolumeAsyncFromPath = -2147024882;
LABEL_15:
        v14 = VolumeAsyncFromPath;
        goto LABEL_16;
      }
      v14 = 0;
      v15 = 1338;
      VolumeAsyncFromPath = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, struct __MIDL___MIDL_itf_dfengine_0000_0000_0007 *))(*(_QWORD *)v18 + 80LL))(
                              v18,
                              v11);
      v14 = VolumeAsyncFromPath;
      v9 = 1342;
      if ( VolumeAsyncFromPath >= 0 )
      {
LABEL_13:
        v15 = v9;
        *a3 = v8;
        *a4 = v11;
        goto LABEL_17;
      }
    }
  }
  else
  {
    *((_DWORD *)this + 39) = 1;
    VolumeAsyncFromPath = CDefragEngine::_CreateVolumeStatusList((__int64)this, 1u, (CDefragEngine *)&v13, &v17);
    v14 = VolumeAsyncFromPath;
    v9 = 1357;
    if ( VolumeAsyncFromPath >= 0 )
    {
      v11 = v13;
      v8 = v17;
      goto LABEL_13;
    }
  }
LABEL_16:
  v16 = v9;
LABEL_17:
  if ( v18 )
    (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v18 + 16LL))(v18);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)VolumeAsyncFromPath;
}

```

## disassembly

```asm
0x18003ee70  mov     [rsp-28h+arg_0], rbx
0x18003ee75  push    rbp
0x18003ee76  push    rsi
0x18003ee77  push    rdi
0x18003ee78  push    r14
0x18003ee7a  push    r15
0x18003ee7c  mov     rbp, rsp
0x18003ee7f  sub     rsp, 60h
0x18003ee83  mov     r14, r9
0x18003ee86  mov     r15, r8
0x18003ee89  mov     rdi, rdx
0x18003ee8c  mov     rbx, rcx
0x18003ee8f  mov     esi, 1
0x18003ee94  mov     r9d, esi; unsigned __int16
0x18003ee97  mov     r8d, 529h; unsigned __int16
0x18003ee9d  lea     rdx, aCdefragengineG_6; "CDefragEngine::GetStatus"
0x18003eea4  lea     rcx, [rbp+var_38]; this
0x18003eea8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003eead  nop
0x18003eeae  mov     [rbp+arg_18], 0
0x18003eeb6  mov     [rbp+var_40], 0
0x18003eebe  mov     [rbp+arg_10], 0
0x18003eec5  test    r14, r14
0x18003eec8  jz      short loc_18003EED1
0x18003eeca  mov     qword ptr [r14], 0
0x18003eed1  mov     eax, 530h
0x18003eed6  test    r15, r15
0x18003eed9  jz      loc_18003EFB6
0x18003eedf  mov     dword ptr [r15], 0
0x18003eee6  mov     [rbp+var_34], ax
0x18003eeea  mov     eax, 531h
0x18003eeef  test    r14, r14
0x18003eef2  jz      loc_18003EFB6
0x18003eef8  mov     [rbp+var_38], 0
0x18003eeff  mov     [rbp+var_34], ax
0x18003ef03  test    rdi, rdi
0x18003ef06  jz      short loc_18003EF7D
0x18003ef08  xor     r9d, r9d; struct CDfVolumeListItem **
0x18003ef0b  lea     r8, [rbp+arg_18]; struct IDefragAsyncWorker **
0x18003ef0f  mov     rdx, rdi; Src
0x18003ef12  mov     rcx, rbx; this
0x18003ef15  call    ?_GetVolumeAsyncFromPath@CDefragEngine@@AEAAJPEBGPEAPEAUIDefragAsyncWorker@@PEAPEAVCDfVolumeListItem@@@Z; CDefragEngine::_GetVolumeAsyncFromPath(ushort const *,IDefragAsyncWorker * *,CDfVolumeListItem * *)
0x18003ef1a  mov     ebx, eax
0x18003ef1c  mov     [rbp+var_38], eax
0x18003ef1f  test    eax, eax
0x18003ef21  mov     eax, 536h
0x18003ef26  js      loc_18003EFBE
0x18003ef2c  mov     [rbp+var_34], ax
0x18003ef30  mov     ecx, 0D0h; cb
0x18003ef35  call    cs:__imp_CoTaskMemAlloc
0x18003ef3b  mov     rdi, rax
0x18003ef3e  test    rax, rax
0x18003ef41  mov     eax, 53Ah
0x18003ef46  jnz     short loc_18003EF4F
0x18003ef48  mov     ebx, 8007000Eh
0x18003ef4d  jmp     short loc_18003EFBB
0x18003ef4f  mov     [rbp+var_38], 0
0x18003ef56  mov     [rbp+var_34], ax
0x18003ef5a  mov     rcx, [rbp+arg_18]
0x18003ef5e  mov     rax, [rcx]
0x18003ef61  mov     rdx, rdi
0x18003ef64  mov     rax, [rax+50h]
0x18003ef68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef6d  mov     ebx, eax
0x18003ef6f  mov     [rbp+var_38], eax
0x18003ef72  test    eax, eax
0x18003ef74  mov     eax, 53Eh
0x18003ef79  js      short loc_18003EFBE
0x18003ef7b  jmp     short loc_18003EFAA
0x18003ef7d  mov     [rbx+9Ch], esi
0x18003ef83  lea     r9, [rbp+arg_10]
0x18003ef87  lea     r8, [rbp+var_40]
0x18003ef8b  mov     edx, esi
0x18003ef8d  mov     rcx, rbx
0x18003ef90  call    ?_CreateVolumeStatusList@CDefragEngine@@AEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0005@@PEAPEAU__MIDL___MIDL_itf_dfengine_0000_0000_0007@@PEAK@Z; CDefragEngine::_CreateVolumeStatusList(__MIDL___MIDL_itf_dfengine_0000_0000_0005,__MIDL___MIDL_itf_dfengine_0000_0000_0007 * *,ulong *)
0x18003ef95  mov     ebx, eax
0x18003ef97  mov     [rbp+var_38], eax
0x18003ef9a  test    eax, eax
0x18003ef9c  mov     eax, 54Dh
0x18003efa1  js      short loc_18003EFBE
0x18003efa3  mov     rdi, [rbp+var_40]
0x18003efa7  mov     esi, [rbp+arg_10]
0x18003efaa  mov     [rbp+var_34], ax
0x18003efae  mov     [r15], esi
0x18003efb1  mov     [r14], rdi
0x18003efb4  jmp     short loc_18003EFC2
0x18003efb6  mov     ebx, 80070057h
0x18003efbb  mov     [rbp+var_38], ebx
0x18003efbe  mov     [rbp+var_32], ax
0x18003efc2  mov     rcx, [rbp+arg_18]
0x18003efc6  test    rcx, rcx
0x18003efc9  jz      short loc_18003EFD8
0x18003efcb  mov     rdx, [rcx]
0x18003efce  mov     rax, [rdx+10h]
0x18003efd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efd7  nop
0x18003efd8  lea     rcx, [rbp+var_38]; this
0x18003efdc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003efe1  mov     eax, ebx
0x18003efe3  mov     rbx, [rsp+60h+arg_0]
0x18003efeb  add     rsp, 60h
0x18003efef  pop     r15
0x18003eff1  pop     r14
0x18003eff3  pop     rdi
0x18003eff4  pop     rsi
0x18003eff5  pop     rbp
0x18003eff6  retn
```
