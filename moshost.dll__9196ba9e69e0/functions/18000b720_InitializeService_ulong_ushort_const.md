# InitializeService(ulong,ushort * * const)

- ea: `0x18000b720`
- end: `0x18000b7d7`
- name: `?InitializeService@@YAJKQEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b8e0`

## callees

- `0x18000ad28`
- `0x18000af38`
- `0x18000b38c`
- `0x18000b720`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b7b8`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b7b8`

## pseudocode

```c
__int64 __fastcall InitializeService(unsigned int a1, unsigned __int16 **const a2)
{
  int v2; // ebx
  int v3; // eax
  int v4; // r8d
  int v5; // eax

  v2 = SvcInitialize(a1, a2);
  if ( v2 >= 0 )
  {
    v3 = RegisterRPCInterface((__int64)L"MosHostSvcRpc\\Interface", qword_18000EC70);
    if ( v3 >= 0 )
    {
      v3 = RegisterRPCInterface((__int64)L"MapsPackageSvcRpc\\Interface", qword_18000F500);
      if ( v3 >= 0 )
      {
        v3 = RegisterRPCInterface((__int64)L"OdmlSvcRpc\\Interface", qword_18000F430);
        if ( v3 >= 0 )
        {
          v3 = RegisterRPCInterface((__int64)L"MapsStorageSvcRpc\\Interface", qword_18000E910);
          if ( v3 >= 0 )
            return 0;
          v4 = 254;
        }
        else
        {
          v4 = 253;
        }
      }
      else
      {
        v4 = 252;
      }
    }
    else
    {
      v4 = 251;
    }
    v5 = ZTraceReportPropagationNoThis(v3, "SvcRegisterRPCInterface", v4);
    v2 = v5;
    if ( v5 < 0 )
      SvcUninitialize(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b720  push    rbx
0x18000b722  sub     rsp, 20h
0x18000b726  call    ?SvcInitialize@@YAJKQEAPEAG@Z; SvcInitialize(ulong,ushort * * const)
0x18000b72b  mov     ebx, eax
0x18000b72d  test    eax, eax
0x18000b72f  js      loc_18000B7CF
0x18000b735  lea     rdx, qword_18000EC70
0x18000b73c  lea     rcx, aMoshostsvcrpcI; "MosHostSvcRpc\\Interface"
0x18000b743  call    RegisterRPCInterface
0x18000b748  test    eax, eax
0x18000b74a  jns     short loc_18000B754
0x18000b74c  mov     r8d, 0FBh
0x18000b752  jmp     short loc_18000B7AF
0x18000b754  lea     rdx, qword_18000F500
0x18000b75b  lea     rcx, aMapspackagesvc_4; "MapsPackageSvcRpc\\Interface"
0x18000b762  call    RegisterRPCInterface
0x18000b767  test    eax, eax
0x18000b769  jns     short loc_18000B773
0x18000b76b  mov     r8d, 0FCh
0x18000b771  jmp     short loc_18000B7AF
0x18000b773  lea     rdx, qword_18000F430
0x18000b77a  lea     rcx, aOdmlsvcrpcInte; "OdmlSvcRpc\\Interface"
0x18000b781  call    RegisterRPCInterface
0x18000b786  test    eax, eax
0x18000b788  jns     short loc_18000B792
0x18000b78a  mov     r8d, 0FDh
0x18000b790  jmp     short loc_18000B7AF
0x18000b792  lea     rdx, qword_18000E910
0x18000b799  lea     rcx, aMapsstoragesvc_6; "MapsStorageSvcRpc\\Interface"
0x18000b7a0  call    RegisterRPCInterface
0x18000b7a5  test    eax, eax
0x18000b7a7  jns     short loc_18000B7CD
0x18000b7a9  mov     r8d, 0FEh
0x18000b7af  lea     rdx, aSvcregisterrpc; "SvcRegisterRPCInterface"
0x18000b7b6  mov     ecx, eax
0x18000b7b8  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b7be  mov     ebx, eax
0x18000b7c0  test    eax, eax
0x18000b7c2  jns     short loc_18000B7CF
0x18000b7c4  mov     ecx, eax; int
0x18000b7c6  call    ?SvcUninitialize@@YAJJ@Z; SvcUninitialize(long)
0x18000b7cb  jmp     short loc_18000B7CF
0x18000b7cd  xor     ebx, ebx
0x18000b7cf  mov     eax, ebx
0x18000b7d1  add     rsp, 20h
0x18000b7d5  pop     rbx
0x18000b7d6  retn
```
