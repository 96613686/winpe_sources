# ScheduleOMADMClientTask(ushort const *,ushort const *)

- ea: `0x1800194bc`
- end: `0x180019558`
- name: `?ScheduleOMADMClientTask@@YAJPEBG0@Z`
- size: `156`
- prototype: `HRESULT __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000be00`

## callees

- `0x180006294`
- `0x1800194bc`
- `0x180019560`
- `0x18001a25c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001953f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019545`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001953f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019545`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800194cd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001950e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800194cd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001950e`

## pseudocode

```c
HRESULT __fastcall ScheduleOMADMClientTask(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT result; // eax
  int v4; // ebx
  HRESULT v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = CoInitializeEx(0, 0);
  if ( result >= 0 )
  {
    v4 = ScheduleOMADMClientTaskHelper(a1);
    if ( v4 >= 0 )
    {
      v4 = ScheduleOMADMClientTaskHelper(a1);
      if ( v4 >= 0 )
      {
        v5 = CoInitializeEx(0, 0);
        v4 = v5;
        if ( v5 >= 0 )
        {
          v4 = ScheduleProvisioningInitiatedSyncHelper(a1);
          CoUninitialize();
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB4,
            (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)v5);
        }
      }
    }
    CoUninitialize();
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800194bc  mov     [rsp+arg_0], rbx
0x1800194c1  push    rdi; int
0x1800194c2  sub     rsp, 20h
0x1800194c6  mov     rdi, rcx
0x1800194c9  xor     edx, edx; dwCoInit
0x1800194cb  xor     ecx, ecx; pvReserved
0x1800194cd  call    cs:__imp_CoInitializeEx
0x1800194d3  test    eax, eax
0x1800194d5  js      short loc_18001954D
0x1800194d7  mov     r9d, 1
0x1800194dd  lea     r8, aScheduleToRunO_0; "Schedule to run OMADMClient by server"
0x1800194e4  mov     rcx, rdi; unsigned __int16 *
0x1800194e7  call    ScheduleOMADMClientTaskHelper
0x1800194ec  mov     ebx, eax
0x1800194ee  test    eax, eax
0x1800194f0  js      short loc_180019545
0x1800194f2  xor     r9d, r9d
0x1800194f5  lea     r8, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x1800194fc  mov     rcx, rdi; unsigned __int16 *
0x1800194ff  call    ScheduleOMADMClientTaskHelper
0x180019504  mov     ebx, eax
0x180019506  test    eax, eax
0x180019508  js      short loc_180019545
0x18001950a  xor     edx, edx; dwCoInit
0x18001950c  xor     ecx, ecx; pvReserved
0x18001950e  call    cs:__imp_CoInitializeEx
0x180019514  mov     ebx, eax
0x180019516  test    eax, eax
0x180019518  jns     short loc_180019535
0x18001951a  mov     rcx, [rsp+28h]; this
0x18001951f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180019526  mov     r9d, eax; char *
0x180019529  mov     edx, 0AB4h; void *
0x18001952e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019533  jmp     short loc_180019545
0x180019535  mov     rcx, rdi; unsigned __int16 *
0x180019538  call    ScheduleProvisioningInitiatedSyncHelper
0x18001953d  mov     ebx, eax
0x18001953f  call    cs:__imp_CoUninitialize
0x180019545  call    cs:__imp_CoUninitialize
0x18001954b  mov     eax, ebx
0x18001954d  mov     rbx, [rsp+28h+arg_0]
0x180019552  add     rsp, 20h
0x180019556  pop     rdi
0x180019557  retn
```
