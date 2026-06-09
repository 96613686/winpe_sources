# CEnumString::AddString(ushort const *)

- ea: `0x1800479b4`
- end: `0x180047a29`
- name: `?AddString@CEnumString@@QEAAJPEBG@Z`
- size: `117`
- prototype: `int(CEnumString *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c6d0`
- `0x18003c960`
- `0x180047ab4`

## callees

- `0x180003c80`
- `0x18003c218`
- `0x1800479b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800479e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800479e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047a11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047a11`

## pseudocode

```c
__int64 __fastcall CEnumString::AddString(CEnumString *this, const unsigned __int16 *a2)
{
  int appended; // edi
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  pv = 0;
  appended = CscUtil_CreateStringCopyForCom(a2, &pv);
  if ( appended >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    appended = CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::AppendPtr((char *)this + 16, pv);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( appended < 0 )
      CoTaskMemFree(pv);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800479b4  mov     r11, rsp
0x1800479b7  mov     [r11+8], rbx
0x1800479bb  mov     [r11+10h], rsi
0x1800479bf  push    rdi
0x1800479c0  sub     rsp, 20h
0x1800479c4  mov     rax, rdx
0x1800479c7  mov     qword ptr [r11+18h], 0
0x1800479cf  mov     rsi, rcx
0x1800479d2  lea     rdx, [r11+18h]; unsigned __int16 **
0x1800479d6  mov     rcx, rax; unsigned __int16 *
0x1800479d9  call    ?CscUtil_CreateStringCopyForCom@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopyForCom(ushort const *,ushort * *)
0x1800479de  mov     edi, eax
0x1800479e0  test    eax, eax
0x1800479e2  js      short loc_180047A17
0x1800479e4  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800479e8  call    cs:__imp_EnterCriticalSection
0x1800479ee  mov     rdx, [rsp+28h+pv]
0x1800479f3  lea     rcx, [rsi+10h]
0x1800479f7  call    ?AppendPtr@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAJPEAGPEAH@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::AppendPtr(ushort *,int *)
0x1800479fc  lea     rcx, [rsi+18h]; lpCriticalSection
0x180047a00  mov     edi, eax
0x180047a02  call    cs:__imp_LeaveCriticalSection
0x180047a08  test    edi, edi
0x180047a0a  jns     short loc_180047A17
0x180047a0c  mov     rcx, [rsp+28h+pv]; pv
0x180047a11  call    cs:__imp_CoTaskMemFree
0x180047a17  mov     rbx, [rsp+28h+arg_0]
0x180047a1c  mov     eax, edi
0x180047a1e  mov     rsi, [rsp+28h+arg_8]
0x180047a23  add     rsp, 20h
0x180047a27  pop     rdi
0x180047a28  retn
```
