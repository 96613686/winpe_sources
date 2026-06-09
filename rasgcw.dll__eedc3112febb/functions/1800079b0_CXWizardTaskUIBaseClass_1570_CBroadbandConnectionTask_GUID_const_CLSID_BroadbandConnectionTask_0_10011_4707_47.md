# CXWizardTaskUIBaseClass<1570,CBroadbandConnectionTask,&_GUID const CLSID_BroadbandConnectionTask,0,10011,4707,4708,4709,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800079b0`
- end: `0x180007a70`
- name: `?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCBroadbandConnectionTask@@$1?CLSID_BroadbandConnectionTask@@3U_GUID@@B$0A@$0CHBL@$0BCGD@$0BCGE@$0BCGF@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *, __int16, int, __int64, __int16, struct IXWizardSource *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800078ac`
- `0x1800079b0`
- `0x18002f382`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007a0b`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CBroadbandConnectionTask,&_GUID const CLSID_BroadbandConnectionTask,0,10011,4707,4708,4709,0>::CanRunTask(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        __int16 a4,
        int a5,
        __int64 a6,
        __int16 a7,
        struct IXWizardSource *a8,
        _QWORD *a9)
{
  __int64 result; // rax
  char *v11; // rax
  char *v12; // rbx

  result = CXWizardTaskBaseClass<1570,CBroadbandConnectionTask,&_GUID const CLSID_BroadbandConnectionTask,0>::CanRunTask(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             a9);
  if ( (int)result >= 0 )
  {
    v11 = (char *)CoTaskMemAlloc(0x60u);
    v12 = v11;
    if ( v11 )
    {
      memset_0(v11 + 8, 0, 0x58u);
      *(_DWORD *)v12 = 96;
      result = 0;
      *((_DWORD *)v12 + 1) = 4;
      *((_QWORD *)v12 + 2) = hInst;
      *((_QWORD *)v12 + 1) = a2;
      *((_QWORD *)v12 + 4) = 4707;
      *((_QWORD *)v12 + 3) = 10011;
      *a9 = v12;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800079b0  mov     r11, rsp
0x1800079b3  mov     [r11+8], rbx
0x1800079b7  mov     [r11+10h], rsi
0x1800079bb  push    rdi
0x1800079bc  sub     rsp, 50h
0x1800079c0  mov     rax, [rsp+58h+arg_38]
0x1800079c8  mov     rdi, rdx
0x1800079cb  mov     rsi, [rsp+58h+arg_40]
0x1800079d3  mov     [r11-18h], rsi
0x1800079d7  mov     [r11-20h], rax
0x1800079db  mov     eax, dword ptr [rsp+58h+arg_30]
0x1800079e2  mov     [rsp+58h+var_28], eax; int
0x1800079e6  mov     rax, [rsp+58h+arg_28]
0x1800079ee  mov     [r11-30h], rax
0x1800079f2  mov     eax, [rsp+58h+arg_20]
0x1800079f9  mov     [rsp+58h+var_38], eax; int
0x1800079fd  call    ?CanRunTask@?$CXWizardTaskBaseClass@$0GCC@VCBroadbandConnectionTask@@$1?CLSID_BroadbandConnectionTask@@3U_GUID@@B$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskBaseClass<1570,CBroadbandConnectionTask,&_GUID const CLSID_BroadbandConnectionTask,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180007a02  test    eax, eax
0x180007a04  js      short loc_180007A60
0x180007a06  mov     ecx, 60h ; '`'; cb
0x180007a0b  call    cs:__imp_CoTaskMemAlloc
0x180007a11  mov     rbx, rax
0x180007a14  test    rax, rax
0x180007a17  jz      short loc_180007A5B
0x180007a19  xor     edx, edx; Val
0x180007a1b  lea     rcx, [rax+8]; void *
0x180007a1f  lea     r8d, [rdx+58h]; Size
0x180007a23  call    memset_0
0x180007a28  mov     dword ptr [rbx], 60h ; '`'
0x180007a2e  xor     eax, eax
0x180007a30  mov     dword ptr [rbx+4], 4
0x180007a37  mov     rcx, cs:hInst
0x180007a3e  mov     [rbx+10h], rcx
0x180007a42  mov     [rbx+8], rdi
0x180007a46  mov     qword ptr [rbx+20h], 1263h
0x180007a4e  mov     qword ptr [rbx+18h], 271Bh
0x180007a56  mov     [rsi], rbx
0x180007a59  jmp     short loc_180007A60
0x180007a5b  mov     eax, 8007000Eh
0x180007a60  mov     rbx, [rsp+58h+arg_0]
0x180007a65  mov     rsi, [rsp+58h+arg_8]
0x180007a6a  add     rsp, 50h
0x180007a6e  pop     rdi
0x180007a6f  retn
```
