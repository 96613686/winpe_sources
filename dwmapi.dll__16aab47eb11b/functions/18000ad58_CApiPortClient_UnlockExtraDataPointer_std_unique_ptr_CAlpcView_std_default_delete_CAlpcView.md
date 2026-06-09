# CApiPortClient::UnlockExtraDataPointer(std::unique_ptr<CAlpcView,std::default_delete<CAlpcView>> &&)

- ea: `0x18000ad58`
- end: `0x18000add8`
- name: `?UnlockExtraDataPointer@CApiPortClient@@QEAAX$$QEAV?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@@Z`
- size: `128`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002920`
- `0x1800052c0`
- `0x1800084b0`
- `0x18000a3c0`
- `0x18000a650`
- `0x18000b908`
- `0x18000b92c`

## callees

- `0x1800075d0`
- `0x18000ad58`
- `0x18000b284`
- `0x18001114c`
- `0x18001512c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad77`

## pseudocode

```c
void __fastcall CApiPortClient::UnlockExtraDataPointer(CApiPortClient *this, __int64 *a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rdx
  char *v7; // [rsp+38h] [rbp+10h] BYREF

  if ( *a2 )
  {
    v7 = (char *)this + 16;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v4 = *(_QWORD *)(*a2 + 32);
    if ( v4 <= 0x10000 )
    {
      v5 = *((_QWORD *)this + 1);
      if ( !v5 || *(_QWORD *)(v5 + 32) < v4 )
        std::unique_ptr<CAlpcView>::operator=<std::default_delete<CAlpcView>,0>((char *)this + 8, a2);
    }
    v6 = *a2;
    *a2 = 0;
    if ( v6 )
      std::default_delete<CAlpcView>::operator()();
    CApiPortClient::DecrementConnectionLock(this);
    CGuard<CDwmCS>::~CGuard<CDwmCS>(&v7);
  }
}

```

## disassembly

```asm
0x18000ad58  mov     [rsp+arg_0], rbx
0x18000ad5d  push    rdi
0x18000ad5e  sub     rsp, 20h
0x18000ad62  cmp     qword ptr [rdx], 0
0x18000ad66  mov     rbx, rdx
0x18000ad69  mov     rdi, rcx
0x18000ad6c  jz      short loc_18000ADCD
0x18000ad6e  add     rcx, 10h; lpCriticalSection
0x18000ad72  mov     [rsp+28h+arg_8], rcx
0x18000ad77  call    cs:__imp_EnterCriticalSection
0x18000ad7d  mov     rax, [rbx]
0x18000ad80  mov     rdx, [rax+20h]
0x18000ad84  cmp     rdx, 10000h
0x18000ad8b  ja      short loc_18000ADA7
0x18000ad8d  lea     rcx, [rdi+8]
0x18000ad91  mov     rax, [rcx]
0x18000ad94  test    rax, rax
0x18000ad97  jz      short loc_18000AD9F
0x18000ad99  cmp     [rax+20h], rdx
0x18000ad9d  jnb     short loc_18000ADA7
0x18000ad9f  mov     rdx, rbx
0x18000ada2  call    ??$?4U?$default_delete@VCAlpcView@@@std@@$0A@@?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CAlpcView>::operator=<std::default_delete<CAlpcView>,0>(std::unique_ptr<CAlpcView> &&)
0x18000ada7  mov     rdx, [rbx]
0x18000adaa  mov     qword ptr [rbx], 0
0x18000adb1  test    rdx, rdx
0x18000adb4  jz      short loc_18000ADBB
0x18000adb6  call    ??R?$default_delete@VCAlpcView@@@std@@QEBAXPEAVCAlpcView@@@Z; std::default_delete<CAlpcView>::operator()(CAlpcView *)
0x18000adbb  mov     rcx, rdi; this
0x18000adbe  call    ?DecrementConnectionLock@CApiPortClient@@AEAAXXZ; CApiPortClient::DecrementConnectionLock(void)
0x18000adc3  lea     rcx, [rsp+28h+arg_8]
0x18000adc8  call    ??1?$CGuard@VCDwmCS@@@@QEAA@XZ; CGuard<CDwmCS>::~CGuard<CDwmCS>(void)
0x18000adcd  mov     rbx, [rsp+28h+arg_0]
0x18000add2  add     rsp, 20h
0x18000add6  pop     rdi
0x18000add7  retn
```
