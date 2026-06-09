# CXWizardTaskUIBaseClass<1570,CBroadbandConnectionTask,&_GUID const CLSID_BroadbandConnectionTask,0,10011,4707,4708,4709,0>::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x180007810`
- end: `0x18000788c`
- name: `?CanHostTask@?$CXWizardTaskUIBaseClass@$0GCC@VCBroadbandConnectionTask@@$1?CLSID_BroadbandConnectionTask@@3U_GUID@@B$0A@$0CHBL@$0BCGD@$0BCGE@$0BCGF@$0A@@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180007810`
- `0x18002f382`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007829`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CBroadbandConnectionTask,&_GUID const CLSID_BroadbandConnectionTask,0,10011,4707,4708,4709,0>::CanHostTask(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 result; // rax

  *a3 = 0;
  v4 = CoTaskMemAlloc(0x40u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  memset_0(v4, 0, 0x40u);
  *v5 = 64;
  result = 0;
  v5[1] = 3;
  *((_QWORD *)v5 + 4) = hInst;
  *((_QWORD *)v5 + 5) = 10011;
  *((_QWORD *)v5 + 6) = 4708;
  *((_QWORD *)v5 + 7) = 4709;
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x180007810  mov     [rsp+arg_0], rbx
0x180007815  push    rdi
0x180007816  sub     rsp, 20h
0x18000781a  mov     ecx, 40h ; '@'; cb
0x18000781f  mov     qword ptr [r8], 0
0x180007826  mov     rdi, r8
0x180007829  call    cs:__imp_CoTaskMemAlloc
0x18000782f  mov     rbx, rax
0x180007832  test    rax, rax
0x180007835  jz      short loc_18000787C
0x180007837  xor     edx, edx; Val
0x180007839  mov     rcx, rax; void *
0x18000783c  lea     r8d, [rdx+40h]; Size
0x180007840  call    memset_0
0x180007845  mov     dword ptr [rbx], 40h ; '@'
0x18000784b  xor     eax, eax
0x18000784d  mov     dword ptr [rbx+4], 3
0x180007854  mov     rcx, cs:hInst
0x18000785b  mov     [rbx+20h], rcx
0x18000785f  mov     qword ptr [rbx+28h], 271Bh
0x180007867  mov     qword ptr [rbx+30h], 1264h
0x18000786f  mov     qword ptr [rbx+38h], 1265h
0x180007877  mov     [rdi], rbx
0x18000787a  jmp     short loc_180007881
0x18000787c  mov     eax, 8007000Eh
0x180007881  mov     rbx, [rsp+28h+arg_0]
0x180007886  add     rsp, 20h
0x18000788a  pop     rdi
0x18000788b  retn
```
