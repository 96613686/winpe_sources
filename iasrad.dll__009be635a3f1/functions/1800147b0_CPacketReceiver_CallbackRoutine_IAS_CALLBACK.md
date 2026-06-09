# CPacketReceiver::CallbackRoutine(IAS_CALLBACK *)

- ea: `0x1800147b0`
- end: `0x180014839`
- name: `?CallbackRoutine@CPacketReceiver@@CAXPEAUIAS_CALLBACK@@@Z`
- size: `137`
- prototype: `void __fastcall(struct IAS_CALLBACK *pv)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094e4`
- `0x1800147b0`
- `0x180015938`
- `0x18001d31c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014826`

## pseudocode

```c
void __fastcall CPacketReceiver::CallbackRoutine(struct IAS_CALLBACK *pv)
{
  int v2; // edx
  CPacketReceiver *i; // rcx

  v2 = *((_DWORD *)pv + 4);
  for ( i = (CPacketReceiver *)*((_QWORD *)pv + 1);
        CPacketReceiver::WorkerRoutine(i, v2);
        i = (CPacketReceiver *)*((_QWORD *)pv + 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("WARNING: reusing WorkerRoutine");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
    }
    v2 = *((_DWORD *)pv + 4);
  }
  CoTaskMemFree(pv);
  _InterlockedDecrement(&g_lThreadCount);
}

```

## disassembly

```asm
0x1800147b0  push    rbx
0x1800147b2  sub     rsp, 20h
0x1800147b6  mov     rbx, rcx
0x1800147b9  mov     edx, [rcx+10h]
0x1800147bc  mov     rcx, [rcx+8]
0x1800147c0  jmp     short loc_18001481A
0x1800147c2  lea     rcx, WPP_GLOBAL_Control
0x1800147c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800147d0  cmp     rax, rcx
0x1800147d3  jz      short loc_180014813
0x1800147d5  cmp     byte ptr [rax+19h], 4
0x1800147d9  jb      short loc_180014813
0x1800147db  test    dword ptr [rax+1Ch], 100h
0x1800147e2  jz      short loc_180014813
0x1800147e4  lea     rcx, aWarningReusing; "WARNING: reusing WorkerRoutine"
0x1800147eb  call    WppDbgPrint
0x1800147f0  mov     edx, 1Bh
0x1800147f5  lea     r9, aNpsrad; "NPSRAD"
0x1800147fc  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180014803  mov     rcx, cs:WPP_GLOBAL_Control
0x18001480a  mov     rcx, [rcx+10h]
0x18001480e  call    WPP_SF_s
0x180014813  mov     edx, [rbx+10h]; unsigned int
0x180014816  mov     rcx, [rbx+8]; this
0x18001481a  call    ?WorkerRoutine@CPacketReceiver@@QEAA_NK@Z; CPacketReceiver::WorkerRoutine(ulong)
0x18001481f  test    al, al
0x180014821  jnz     short loc_1800147C2
0x180014823  mov     rcx, rbx; pv
0x180014826  call    cs:__imp_CoTaskMemFree
0x18001482c  lock dec cs:?g_lThreadCount@@3JA; long g_lThreadCount
0x180014833  add     rsp, 20h
0x180014837  pop     rbx
0x180014838  retn
```
