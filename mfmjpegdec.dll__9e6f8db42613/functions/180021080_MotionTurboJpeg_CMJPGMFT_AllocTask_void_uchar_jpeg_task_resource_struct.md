# MotionTurboJpeg::CMJPGMFT::AllocTask(void *,uchar,jpeg_task_resource_struct * *)

- ea: `0x180021080`
- end: `0x180021144`
- name: `?AllocTask@CMJPGMFT@MotionTurboJpeg@@SAEPEAXEPEAPEAUjpeg_task_resource_struct@@@Z`
- size: `196`
- prototype: `unsigned __int8 __fastcall(void *, unsigned __int8, struct jpeg_task_resource_struct **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ced0`
- `0x18001e0ec`
- `0x180021080`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x1800210e0`
- `MFPlat!MFCreateAsyncResult` at `0x1800210e0`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800210fd`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800210fd`

## pseudocode

```c
unsigned __int8 __fastcall MotionTurboJpeg::CMJPGMFT::AllocTask(
        void *a1,
        char a2,
        struct jpeg_task_resource_struct **a3)
{
  IMFAsyncResult *v5; // rcx
  IMFAsyncResult *ppAsyncResult; // [rsp+30h] [rbp+8h] BYREF
  MFWORKITEM_KEY pKey; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  *a3 = (struct jpeg_task_resource_struct *)MotionTurboJpeg::CMJPGMFT::CSlimQueue<jpeg_task_resource_struct *,4>::GetWait((PSRWLOCK)a1 + 27);
  if ( !a2 )
  {
    pKey = 0;
    ppAsyncResult = 0;
    Microsoft::WRL::ComPtr<IMFAsyncResult>::InternalRelease(&ppAsyncResult);
    if ( MFCreateAsyncResult(0, (IMFAsyncCallback *)a1 + 18, 0, &ppAsyncResult)
      || !MFPutWaitingWorkItem(*((HANDLE *)a1 + 35), 0, ppAsyncResult, &pKey) )
    {
      Microsoft::WRL::ComPtr<IMFAsyncResult>::InternalRelease(&ppAsyncResult);
    }
    else
    {
      v5 = ppAsyncResult;
      if ( ppAsyncResult )
      {
        ppAsyncResult = 0;
        ((void (__fastcall *)(IMFAsyncResult *))v5->lpVtbl->Release)(v5);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180021080  mov     [rsp+arg_8], rbx
0x180021085  mov     [rsp+arg_18], rsi
0x18002108a  push    rdi
0x18002108b  sub     rsp, 20h
0x18002108f  mov     rsi, rcx
0x180021092  mov     qword ptr [r8], 0
0x180021099  add     rcx, 0D8h; SRWLock
0x1800210a0  mov     rbx, r8
0x1800210a3  mov     dil, dl
0x1800210a6  call    ?GetWait@?$CSlimQueue@PEAUjpeg_task_resource_struct@@$03@CMJPGMFT@MotionTurboJpeg@@QEAAPEAUjpeg_task_resource_struct@@XZ; MotionTurboJpeg::CMJPGMFT::CSlimQueue<jpeg_task_resource_struct *,4>::GetWait(void)
0x1800210ab  mov     [rbx], rax
0x1800210ae  test    dil, dil
0x1800210b1  jnz     short loc_180021132
0x1800210b3  lea     rcx, [rsp+28h+ppAsyncResult]
0x1800210b8  mov     [rsp+28h+pKey], 0
0x1800210c1  mov     [rsp+28h+ppAsyncResult], 0
0x1800210ca  call    ?InternalRelease@?$ComPtr@UIMFAsyncResult@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAsyncResult>::InternalRelease(void)
0x1800210cf  lea     rdx, [rsi+90h]; pCallback
0x1800210d6  xor     r8d, r8d; punkState
0x1800210d9  lea     r9, [rsp+28h+ppAsyncResult]; ppAsyncResult
0x1800210de  xor     ecx, ecx; punkObject
0x1800210e0  call    cs:__imp_MFCreateAsyncResult
0x1800210e6  test    eax, eax
0x1800210e8  jnz     short loc_180021128
0x1800210ea  mov     r8, [rsp+28h+ppAsyncResult]; pResult
0x1800210ef  lea     r9, [rsp+28h+pKey]; pKey
0x1800210f4  mov     rcx, [rsi+118h]; hEvent
0x1800210fb  xor     edx, edx; Priority
0x1800210fd  call    cs:__imp_MFPutWaitingWorkItem
0x180021103  test    eax, eax
0x180021105  jz      short loc_180021128
0x180021107  mov     rcx, [rsp+28h+ppAsyncResult]
0x18002110c  test    rcx, rcx
0x18002110f  jz      short loc_180021132
0x180021111  mov     [rsp+28h+ppAsyncResult], 0
0x18002111a  mov     rax, [rcx]
0x18002111d  mov     rax, [rax+10h]
0x180021121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021126  jmp     short loc_180021132
0x180021128  lea     rcx, [rsp+28h+ppAsyncResult]
0x18002112d  call    ?InternalRelease@?$ComPtr@UIMFAsyncResult@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFAsyncResult>::InternalRelease(void)
0x180021132  mov     rbx, [rsp+28h+arg_8]
0x180021137  mov     al, 1
0x180021139  mov     rsi, [rsp+28h+arg_18]
0x18002113e  add     rsp, 20h
0x180021142  pop     rdi
0x180021143  retn
```
