# CServiceCallback::GetTeredoReference(IUnknown * *)

- ea: `0x18000a4d0`
- end: `0x18000a531`
- name: `?GetTeredoReference@CServiceCallback@@EEBAJPEAPEAUIUnknown@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(CServiceCallback *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002200`
- `0x180003d28`
- `0x18000a4d0`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetTeredoReference(CServiceCallback *this, struct IUnknown **a2)
{
  int v3; // ebx
  struct IUnknown *v5; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v5);
  v3 = Microsoft::WRL::Details::MakeAndInitialize<CTeredoConsumer,IUnknown,>(&v5);
  if ( v3 >= 0 )
  {
    v3 = 0;
    *a2 = v5;
    v5 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a4d0  mov     [rsp+arg_0], rbx
0x18000a4d5  push    rdi
0x18000a4d6  sub     rsp, 20h
0x18000a4da  lea     rcx, [rsp+28h+arg_8]
0x18000a4df  mov     qword ptr [rdx], 0
0x18000a4e6  mov     rdi, rdx
0x18000a4e9  mov     [rsp+28h+arg_8], 0
0x18000a4f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a4f7  lea     rcx, [rsp+28h+arg_8]
0x18000a4fc  call    ??$MakeAndInitialize@VCTeredoConsumer@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CTeredoConsumer,IUnknown,>(IUnknown * *)
0x18000a501  mov     ebx, eax
0x18000a503  test    eax, eax
0x18000a505  js      short loc_18000A51A
0x18000a507  mov     rax, [rsp+28h+arg_8]
0x18000a50c  xor     ebx, ebx
0x18000a50e  mov     [rdi], rax
0x18000a511  mov     [rsp+28h+arg_8], 0
0x18000a51a  lea     rcx, [rsp+28h+arg_8]
0x18000a51f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a524  mov     eax, ebx
0x18000a526  mov     rbx, [rsp+28h+arg_0]
0x18000a52b  add     rsp, 20h
0x18000a52f  pop     rdi
0x18000a530  retn
```
