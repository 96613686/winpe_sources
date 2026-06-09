# NDXGI::CDevice::Trim(void)

- ea: `0x180042e60`
- end: `0x180042f5e`
- name: `?Trim@CDevice@NDXGI@@UEAAXXZ`
- size: `254`
- prototype: `void __fastcall(NDXGI::CDevice *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180043008`

## callees

- `0x18001e2a0`
- `0x18002bd20`
- `0x18002d0f0`
- `0x18002e160`
- `0x18002fc40`
- `0x180042e60`
- `0x180042f64`
- `0x180043008`
- `0x1800430ec`
- `0x180167424`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180042f56`
- `ntdll!EtwEventWrite` at `0x180042f56`

## pseudocode

```c
void __fastcall NDXGI::CDevice::Trim(void **this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _BYTE v6[48]; // [rsp+30h] [rbp-38h] BYREF
  int v7; // [rsp+70h] [rbp+8h] BYREF
  char v8; // [rsp+78h] [rbp+10h] BYREF

  CETWEvent_IDXGIDevice3_Trim::CETWEvent_IDXGIDevice3_Trim((CETWEvent_IDXGIDevice3_Trim *)&v8, this[10]);
  CLockOwnerChild<CDevice,0>::UCAddUse((unsigned __int64)(this + 6) & -(__int64)(this != 0));
  NDXGI::CDevice::TrimRuntimeMemory((NDXGI::CDevice *)this);
  v2 = *((_QWORD *)this[9] + 135);
  *(_BYTE *)(v2 + 3700) = 1;
  if ( *(_DWORD *)(v2 + 39304) )
    CContext::FlushMarkerData((CContext *)v2);
  CDevCtxInterface::CDevCtxInterface((CDevCtxInterface *)v6, (struct CContext *)v2, 1, 0, 0);
  NDXGI::CDevice::Flush((NDXGI::CDevice *)(this + 2), 4u);
  v4 = this[12];
  v5 = v4[105];
  if ( v5 )
  {
    v7 = 0;
    v7 = *((_DWORD *)v4 + 24);
    CallAndLogImpl<long (*)(_D3DKMT_FLUSHHEAPTRANSITIONS *),_D3DKMT_FLUSHHEAPTRANSITIONS *>(v5, v3, &v7);
  }
  CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v6);
  CLockOwnerChild<CDevice,0>::UCReleaseUse((unsigned __int64)(this + 6) & -(__int64)(this != 0));
  if ( v8 )
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, &IDXGIDevice3_Trim_Stop, 0, 0);
}

```

## disassembly

```asm
0x180042e60  mov     [rsp+arg_10], rbx
0x180042e65  mov     [rsp+arg_18], rsi
0x180042e6a  push    rdi
0x180042e6b  sub     rsp, 60h
0x180042e6f  mov     rbx, rcx
0x180042e72  mov     rdx, [rcx+50h]; void *
0x180042e76  lea     rcx, [rsp+68h+arg_8]; this
0x180042e7b  call    ??0CETWEvent_IDXGIDevice3_Trim@@QEAA@PEAX@Z; CETWEvent_IDXGIDevice3_Trim::CETWEvent_IDXGIDevice3_Trim(void *)
0x180042e80  mov     rax, rbx
0x180042e83  lea     rdx, [rbx+30h]
0x180042e87  neg     rax
0x180042e8a  sbb     rsi, rsi
0x180042e8d  and     rsi, rdx
0x180042e90  mov     rcx, rsi
0x180042e93  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x180042e98  mov     rcx, rbx; this
0x180042e9b  call    ?TrimRuntimeMemory@CDevice@NDXGI@@QEAAXXZ; NDXGI::CDevice::TrimRuntimeMemory(void)
0x180042ea0  mov     rax, [rbx+48h]
0x180042ea4  mov     rdi, [rax+438h]
0x180042eab  mov     byte ptr [rdi+0E74h], 1
0x180042eb2  cmp     dword ptr [rdi+9988h], 0
0x180042eb9  jnz     short loc_180042F35
0x180042ebb  mov     [rsp+68h+var_48], 0; bool
0x180042ec0  xor     r9d, r9d; bool
0x180042ec3  mov     r8b, 1; bool
0x180042ec6  mov     rdx, rdi; struct CContext *
0x180042ec9  lea     rcx, [rsp+68h+var_38]; this
0x180042ece  call    ??$?0VCContext@@@CDevCtxInterface@@QEAA@PEAVCContext@@_N11@Z; CDevCtxInterface::CDevCtxInterface(CContext *,bool,bool,bool)
0x180042ed3  lea     rcx, [rbx+10h]; this
0x180042ed7  mov     edx, 4; unsigned int
0x180042edc  call    ?Flush@CDevice@NDXGI@@UEAAHI@Z; NDXGI::CDevice::Flush(uint)
0x180042ee1  mov     rax, [rbx+60h]
0x180042ee5  mov     rcx, [rax+348h]
0x180042eec  test    rcx, rcx
0x180042eef  jz      short loc_180042F0A
0x180042ef1  mov     [rsp+68h+arg_0], 0
0x180042ef9  mov     eax, [rax+60h]
0x180042efc  mov     [rsp+68h+arg_0], eax
0x180042f00  lea     r8, [rsp+68h+arg_0]
0x180042f05  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_FLUSHHEAPTRANSITIONS@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_FLUSHHEAPTRANSITIONS@@@ZPEBD0@Z; CallAndLogImpl<long (*)(_D3DKMT_FLUSHHEAPTRANSITIONS *),_D3DKMT_FLUSHHEAPTRANSITIONS *>(long (*)(_D3DKMT_FLUSHHEAPTRANSITIONS *),char const *,_D3DKMT_FLUSHHEAPTRANSITIONS *)
0x180042f0a  lea     rcx, [rsp+68h+var_38]; this
0x180042f0f  call    ??1CDevCtxInterface@@QEAA@XZ; CDevCtxInterface::~CDevCtxInterface(void)
0x180042f14  mov     rcx, rsi
0x180042f17  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x180042f1c  cmp     [rsp+68h+arg_8], 0
0x180042f21  jnz     short loc_180042F42
0x180042f23  lea     r11, [rsp+68h+var_8]
0x180042f28  mov     rbx, [r11+20h]
0x180042f2c  mov     rsi, [r11+28h]
0x180042f30  mov     rsp, r11
0x180042f33  pop     rdi
0x180042f34  retn
0x180042f35  mov     rcx, rdi; this
0x180042f38  call    ?FlushMarkerData@CContext@@QEAAXXZ; CContext::FlushMarkerData(void)
0x180042f3d  jmp     loc_180042EBB
0x180042f42  xor     r9d, r9d
0x180042f45  xor     r8d, r8d
0x180042f48  lea     rdx, IDXGIDevice3_Trim_Stop
0x180042f4f  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x180042f56  call    cs:__imp_EtwEventWrite
0x180042f5c  jmp     short loc_180042F23
```
