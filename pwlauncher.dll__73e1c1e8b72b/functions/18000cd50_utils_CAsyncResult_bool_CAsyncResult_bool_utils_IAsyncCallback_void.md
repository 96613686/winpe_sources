# utils::CAsyncResult<bool>::CAsyncResult<bool>(utils::IAsyncCallback *,void *)

- ea: `0x18000cd50`
- end: `0x18000ce48`
- name: `??0?$CAsyncResult@_N@utils@@QEAA@PEAVIAsyncCallback@1@PEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ab94`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x18000cd50`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000cd94`
- `KERNEL32!CreateEventW` at `0x18000cd94`
- `KERNEL32!GetLastError` at `0x18000cdc6`
- `KERNEL32!GetLastError` at `0x18000cdc6`

## pseudocode

```c
__int64 __fastcall utils::CAsyncResult<bool>::CAsyncResult<bool>(__int64 a1, __int64 a2, __int64 a3)
{
  signed int LastError; // eax
  unsigned int v6; // edx
  char v7; // r8
  __int64 pExceptionObject; // [rsp+50h] [rbp+18h] BYREF

  pExceptionObject = a3;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &utils::CAsyncResultNoResult::`vftable';
  *(_QWORD *)(a1 + 24) = a2;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = CreateEventW(0, 1, 0, 0);
  *(_DWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 52) = 0;
  if ( !*(_QWORD *)(a1 + 40) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    else
      v6 = LastError;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_d91e401e6ac0313360b28a264a83eb95_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\casyncresultnoresult.cpp",
        48,
        v7);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  *(_QWORD *)a1 = &utils::CAsyncResult<bool>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x18000cd50  mov     [rsp+pExceptionObject], r8
0x18000cd55  mov     [rsp+arg_0], rcx
0x18000cd5a  push    rbx
0x18000cd5b  sub     rsp, 30h
0x18000cd5f  mov     rbx, rcx
0x18000cd62  mov     qword ptr [rcx+8], 0
0x18000cd6a  mov     qword ptr [rcx+10h], 0
0x18000cd72  lea     rax, ??_7CAsyncResultNoResult@utils@@6B@; const utils::CAsyncResultNoResult::`vftable'
0x18000cd79  mov     [rcx], rax
0x18000cd7c  mov     [rcx+18h], rdx
0x18000cd80  mov     qword ptr [rcx+20h], 0
0x18000cd88  xor     r9d, r9d; lpName
0x18000cd8b  xor     r8d, r8d; bInitialState
0x18000cd8e  lea     edx, [r9+1]; bManualReset
0x18000cd92  xor     ecx, ecx; lpEventAttributes
0x18000cd94  call    cs:__imp_CreateEventW
0x18000cd9a  mov     [rbx+28h], rax
0x18000cd9e  mov     dword ptr [rbx+30h], 0
0x18000cda5  mov     dword ptr [rbx+34h], 0
0x18000cdac  cmp     qword ptr [rbx+28h], 0
0x18000cdb1  jz      short loc_18000CDC6
0x18000cdb3  lea     rax, ??_7?$CAsyncResult@_N@utils@@6B@; const utils::CAsyncResult<bool>::`vftable'
0x18000cdba  mov     [rbx], rax
0x18000cdbd  mov     rax, rbx
0x18000cdc0  add     rsp, 30h
0x18000cdc4  pop     rbx
0x18000cdc5  retn
0x18000cdc6  call    cs:__imp_GetLastError
0x18000cdcc  nop
0x18000cdcd  mov     r8d, eax
0x18000cdd0  test    eax, eax
0x18000cdd2  jg      short loc_18000CDD8
0x18000cdd4  mov     edx, eax
0x18000cdd6  jmp     short loc_18000CDE2
0x18000cdd8  movzx   edx, r8w
0x18000cddc  or      edx, 80070000h; int
0x18000cde2  lea     rcx, [rsp+38h+pExceptionObject]; this
0x18000cde7  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000cdec  lea     rax, WPP_GLOBAL_Control
0x18000cdf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdfa  cmp     rcx, rax
0x18000cdfd  jz      short loc_18000CE2E
0x18000cdff  test    byte ptr [rcx+1Ch], 1
0x18000ce03  jz      short loc_18000CE2E
0x18000ce05  mov     edx, 0Ah
0x18000ce0a  mov     [rsp+38h+var_10], r8d
0x18000ce0f  mov     [rsp+38h+var_18], 30h ; '0'
0x18000ce17  lea     r9, aDriversWdmUsbp_14; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000ce1e  lea     r8, WPP_d91e401e6ac0313360b28a264a83eb95_Traceguids
0x18000ce25  mov     rcx, [rcx+10h]
0x18000ce29  call    WPP_SF_sdD
0x18000ce2e  mov     eax, dword ptr [rsp+38h+pExceptionObject]
0x18000ce32  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x18000ce36  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000ce3d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000ce42  call    _CxxThrowException_0
```
