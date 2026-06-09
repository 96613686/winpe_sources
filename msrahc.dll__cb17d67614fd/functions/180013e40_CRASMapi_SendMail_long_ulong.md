# CRASMapi::SendMail(long *,ulong *)

- ea: `0x180013e40`
- end: `0x180013fe1`
- name: `?SendMail@CRASMapi@@UEAAJPEAJPEAK@Z`
- size: `417`
- prototype: `__int64 __fastcall(HMODULE *this, struct _EVENT_DESCRIPTOR *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180012a74`
- `0x180012f5c`
- `0x180013e40`
- `0x180014660`
- `0x180014814`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180013f31`
- `KERNEL32!CreateThread` at `0x180013f31`
- `KERNEL32!GetProcAddress` at `0x180013ecb`
- `KERNEL32!GetProcAddress` at `0x180013ecb`
- `KERNEL32!WaitForSingleObject` at `0x180013f56`
- `KERNEL32!WaitForSingleObject` at `0x180013f56`

## pseudocode

```c
__int64 __fastcall CRASMapi::SendMail(HMODULE *this, struct _EVENT_DESCRIPTOR *a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  CEventLogger *v7; // rcx
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  signed int v10; // eax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  HANDLE Thread; // rax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  unsigned __int16 *v16; // r9
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  unsigned __int16 *v19; // r9
  unsigned int v20; // eax
  LPVOID lpParameter; // [rsp+48h] [rbp+10h] BYREF

  lpParameter = 0;
  lpfnMapiSendMail = 0;
  if ( a2 )
  {
    *(_DWORD *)&a2->Id = 0;
    if ( *((_DWORD *)this + 271) )
    {
      lpfnMapiSendMail = (__int64)GetProcAddress(this[2], "MAPISendMail");
      if ( lpfnMapiSendMail )
      {
        v10 = CRASMapi::BuildMAPIMessage((LPCWCH *)this, (struct MapiMessage **)&lpParameter);
        v6 = v10;
        if ( v10 >= 0 )
        {
          Thread = CreateThread(0, 0, SmapiCallThreadFunction, lpParameter, 0, 0);
          if ( Thread )
          {
            if ( !WaitForSingleObject(Thread, 0xFFFFFFFF) )
            {
              CEventLogger::LogEvent(v7, &Enter_Conditional_Block, 0x1BAu, v16);
              v20 = SendMailError;
              *a3 = SendMailError;
              if ( v20 )
              {
                v6 = -2147467259;
                CEventLogger::LogError(
                  v18,
                  v17,
                  L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
                  0x1C7u,
                  L"CRASMapi::SendMail",
                  0);
              }
              else
              {
                *(_DWORD *)&a2->Id = 1;
                v6 = 0;
              }
              CEventLogger::LogEvent(v18, &Exit_Conditional_Block, 0x1CBu, v19);
            }
          }
          else
          {
            v6 = -2147467259;
            CEventLogger::LogError(
              v15,
              v14,
              L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
              0x1B2u,
              L"CRASMapi::SendMail",
              0);
          }
        }
        else
        {
          CEventLogger::LogError(
            v12,
            v11,
            L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
            0x1A4u,
            L"CRASMapi::SendMail",
            v10);
        }
      }
      else
      {
        v6 = -2147467259;
        CEventLogger::LogError(
          v9,
          v8,
          L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
          0x19Eu,
          L"CRASMapi::SendMail",
          0);
      }
    }
    else
    {
      v6 = 1;
      CEventLogger::LogError(
        (CEventLogger *)this,
        a2,
        L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
        0x195u,
        L"CRASMapi::SendMail",
        1u);
    }
  }
  else
  {
    v6 = -2147467261;
    CEventLogger::LogError(
      (CEventLogger *)this,
      0,
      L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
      0x18Bu,
      L"CRASMapi::SendMail",
      0x80004003);
  }
  CRASMapi::FreeMAPIMessage(v7, (struct MapiMessage **)&lpParameter);
  return v6;
}

```

## disassembly

```asm
0x180013e40  mov     rax, rsp
0x180013e43  mov     [rax+8], rbx
0x180013e47  mov     [rax+18h], rsi
0x180013e4b  push    rdi
0x180013e4c  sub     rsp, 30h
0x180013e50  mov     qword ptr [rax+10h], 0
0x180013e58  mov     rsi, r8
0x180013e5b  mov     cs:?lpfnMapiSendMail@@3P6AK_K0PEAUMapiMessage@@KK@_EEA, 0
0x180013e66  mov     rdi, rdx
0x180013e69  mov     rbx, rcx
0x180013e6c  test    rdx, rdx
0x180013e6f  jnz     short loc_180013EA0
0x180013e71  mov     ebx, 80004003h
0x180013e76  mov     dword ptr [rax-10h], 80004003h
0x180013e7d  mov     r9d, 18Bh; unsigned int
0x180013e83  lea     rax, aCrasmapiSendma; "CRASMapi::SendMail"
0x180013e8a  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\rahelperclass\\ras"...
0x180013e91  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x180013e96  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180013e9b  jmp     loc_180013FC5
0x180013ea0  mov     dword ptr [rdx], 0
0x180013ea6  cmp     dword ptr [rcx+43Ch], 0
0x180013ead  jnz     short loc_180013EC0
0x180013eaf  mov     ebx, 1
0x180013eb4  mov     r9d, 195h
0x180013eba  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x180013ebe  jmp     short loc_180013E83
0x180013ec0  mov     rcx, [rcx+10h]; hModule
0x180013ec4  lea     rdx, aMapisendmail; "MAPISendMail"
0x180013ecb  call    cs:__imp_GetProcAddress
0x180013ed1  mov     cs:?lpfnMapiSendMail@@3P6AK_K0PEAUMapiMessage@@KK@_EEA, rax
0x180013ed8  test    rax, rax
0x180013edb  jnz     short loc_180013EEE
0x180013edd  mov     ebx, 80004005h
0x180013ee2  mov     dword ptr [rsp+38h+lpThreadId], eax
0x180013ee6  mov     r9d, 19Eh
0x180013eec  jmp     short loc_180013E83
0x180013eee  lea     rdx, [rsp+38h+lpParameter]; struct MapiMessage **
0x180013ef3  mov     rcx, rbx; this
0x180013ef6  call    ?BuildMAPIMessage@CRASMapi@@AEAAJPEAPEAUMapiMessage@@@Z; CRASMapi::BuildMAPIMessage(MapiMessage * *)
0x180013efb  mov     ebx, eax
0x180013efd  test    eax, eax
0x180013eff  jns     short loc_180013F10
0x180013f01  mov     dword ptr [rsp+38h+lpThreadId], eax
0x180013f05  mov     r9d, 1A4h
0x180013f0b  jmp     loc_180013E83
0x180013f10  mov     r9, [rsp+38h+lpParameter]; lpParameter
0x180013f15  lea     r8, ?SmapiCallThreadFunction@@YAKPEAX@Z; lpStartAddress
0x180013f1c  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180013f25  xor     edx, edx; dwStackSize
0x180013f27  xor     ecx, ecx; lpThreadAttributes
0x180013f29  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180013f31  call    cs:__imp_CreateThread
0x180013f37  test    rax, rax
0x180013f3a  jnz     short loc_180013F50
0x180013f3c  mov     ebx, 80004005h
0x180013f41  mov     dword ptr [rsp+38h+lpThreadId], eax
0x180013f45  mov     r9d, 1B2h
0x180013f4b  jmp     loc_180013E83
0x180013f50  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013f53  mov     rcx, rax; hHandle
0x180013f56  call    cs:__imp_WaitForSingleObject
0x180013f5c  test    eax, eax
0x180013f5e  jnz     short loc_180013FC5
0x180013f60  mov     r8d, 1BAh; unsigned int
0x180013f66  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x180013f6d  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x180013f72  mov     eax, cs:?SendMailError@@3KA; ulong SendMailError
0x180013f78  mov     [rsi], eax
0x180013f7a  test    eax, eax
0x180013f7c  jnz     short loc_180013F88
0x180013f7e  mov     dword ptr [rdi], 1
0x180013f84  xor     ebx, ebx
0x180013f86  jmp     short loc_180013FB3
0x180013f88  lea     rax, aCrasmapiSendma; "CRASMapi::SendMail"
0x180013f8f  mov     dword ptr [rsp+38h+lpThreadId], 0; unsigned int
0x180013f97  mov     r9d, 1C7h; unsigned int
0x180013f9d  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x180013fa2  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\rahelperclass\\ras"...
0x180013fa9  mov     ebx, 80004005h
0x180013fae  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180013fb3  mov     r8d, 1CBh; unsigned int
0x180013fb9  lea     rdx, Exit_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x180013fc0  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x180013fc5  lea     rdx, [rsp+38h+lpParameter]; struct MapiMessage **
0x180013fca  call    ?FreeMAPIMessage@CRASMapi@@AEAAJPEAPEAUMapiMessage@@@Z; CRASMapi::FreeMAPIMessage(MapiMessage * *)
0x180013fcf  mov     rsi, [rsp+38h+arg_10]
0x180013fd4  mov     eax, ebx
0x180013fd6  mov     rbx, [rsp+38h+arg_0]
0x180013fdb  add     rsp, 30h
0x180013fdf  pop     rdi
0x180013fe0  retn
```
