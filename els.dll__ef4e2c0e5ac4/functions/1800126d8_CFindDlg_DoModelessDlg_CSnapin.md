# CFindDlg::DoModelessDlg(CSnapin *)

- ea: `0x1800126d8`
- end: `0x180012794`
- name: `?DoModelessDlg@CFindDlg@@QEAAJPEAVCSnapin@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CFindDlg *__hidden this, struct CSnapin *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x1800126d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001274d`
- `KERNEL32!CloseHandle` at `0x18001274d`
- `KERNEL32!CreateThread` at `0x18001273f`
- `KERNEL32!CreateThread` at `0x18001273f`
- `KERNEL32!GetLastError` at `0x180012755`
- `KERNEL32!GetLastError` at `0x180012755`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x180012773`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x180012773`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18001270b`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18001270b`

## pseudocode

```c
HRESULT __fastcall CFindDlg::DoModelessDlg(LPSTREAM *this, IUnknown *a2)
{
  HRESULT result; // eax
  IStream **v4; // rdi
  HRESULT InterfaceAndReleaseStream; // ebx
  HANDLE v6; // rax
  IStream *v7; // rcx
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
    return -2147467261;
  v4 = this + 4;
  result = CoMarshalInterThreadInterfaceInStream(&IID_IResultPrshtActions, a2 + 5, this + 4);
  InterfaceAndReleaseStream = result;
  if ( result >= 0 )
  {
    ThreadId = 0;
    v6 = CreateThread(0, 0, CFindDlg::_ThreadFunc, this, 0, &ThreadId);
    if ( v6 )
    {
      CloseHandle(v6);
    }
    else
    {
      GetLastError();
      v7 = *v4;
      ppv = 0;
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v7, &IID_IResultPrshtActions, &ppv);
      *v4 = 0;
    }
    return InterfaceAndReleaseStream;
  }
  return result;
}

```

## disassembly

```asm
0x1800126d8  mov     [rsp+arg_0], rbx
0x1800126dd  mov     [rsp+arg_18], rsi
0x1800126e2  push    rdi
0x1800126e3  sub     rsp, 30h
0x1800126e7  mov     rsi, rcx
0x1800126ea  test    rdx, rdx
0x1800126ed  jnz     short loc_1800126F9
0x1800126ef  mov     eax, 80004003h
0x1800126f4  jmp     loc_180012784
0x1800126f9  lea     rdi, [rcx+20h]
0x1800126fd  add     rdx, 28h ; '('; pUnk
0x180012701  mov     r8, rdi; ppStm
0x180012704  lea     rcx, IID_IResultPrshtActions; riid
0x18001270b  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180012711  mov     ebx, eax
0x180012713  test    eax, eax
0x180012715  js      short loc_180012784
0x180012717  lea     rax, [rsp+38h+ThreadId]
0x18001271c  mov     [rsp+38h+ThreadId], 0
0x180012724  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180012729  lea     r8, ?_ThreadFunc@CFindDlg@@CAKPEAX@Z; lpStartAddress
0x180012730  mov     r9, rsi; lpParameter
0x180012733  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001273b  xor     edx, edx; dwStackSize
0x18001273d  xor     ecx, ecx; lpThreadAttributes
0x18001273f  call    cs:__imp_CreateThread
0x180012745  test    rax, rax
0x180012748  jz      short loc_180012755
0x18001274a  mov     rcx, rax; hObject
0x18001274d  call    cs:__imp_CloseHandle
0x180012753  jmp     short loc_180012782
0x180012755  call    cs:__imp_GetLastError
0x18001275b  mov     rcx, [rdi]; pStm
0x18001275e  lea     r8, [rsp+38h+ppv]; ppv
0x180012763  lea     rdx, IID_IResultPrshtActions; iid
0x18001276a  mov     [rsp+38h+ppv], 0
0x180012773  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180012779  mov     ebx, eax
0x18001277b  mov     qword ptr [rdi], 0
0x180012782  mov     eax, ebx
0x180012784  mov     rbx, [rsp+38h+arg_0]
0x180012789  mov     rsi, [rsp+38h+arg_18]
0x18001278e  add     rsp, 30h
0x180012792  pop     rdi
0x180012793  retn
```
