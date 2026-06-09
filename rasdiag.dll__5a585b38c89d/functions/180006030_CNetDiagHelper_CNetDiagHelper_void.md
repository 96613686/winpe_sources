# CNetDiagHelper::~CNetDiagHelper(void)

- ea: `0x180006030`
- end: `0x1800060a8`
- name: `??1CNetDiagHelper@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CNetDiagHelper *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800060b0`
- `0x180008280`
- `0x180009a6c`
- `0x18000aa20`

## callees

- `0x180006030`
- `0x18000678c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180006090`
- `KERNEL32!DeleteCriticalSection` at `0x180006090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006067`

## pseudocode

```c
void __fastcall CNetDiagHelper::~CNetDiagHelper(CNetDiagHelper *this)
{
  __int64 i; // rdi

  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((_attribute_t *)(*((_QWORD *)this + 4) + 144 * i));
  }
  CoTaskMemFree(*((LPVOID *)this + 4));
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( *((_BYTE *)this + 104) )
  {
    *((_BYTE *)this + 104) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  }
}

```

## disassembly

```asm
0x180006030  mov     [rsp+arg_0], rbx
0x180006035  push    rdi
0x180006036  sub     rsp, 20h
0x18000603a  cmp     qword ptr [rcx+20h], 0
0x18000603f  mov     rbx, rcx
0x180006042  jz      short loc_180006063
0x180006044  xor     edi, edi
0x180006046  cmp     [rcx+18h], edi
0x180006049  jbe     short loc_180006063
0x18000604b  lea     rcx, [rdi+rdi*8]
0x18000604f  shl     rcx, 4
0x180006053  add     rcx, [rbx+20h]; this
0x180006057  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000605c  inc     edi
0x18000605e  cmp     edi, [rbx+18h]
0x180006061  jb      short loc_18000604B
0x180006063  mov     rcx, [rbx+20h]; pv
0x180006067  call    cs:__imp_CoTaskMemFree
0x18000606e  nop     dword ptr [rax+rax+00h]
0x180006073  lea     rcx, [rbx+40h]; lpCriticalSection
0x180006077  mov     qword ptr [rbx+20h], 0
0x18000607f  mov     dword ptr [rbx+18h], 0
0x180006086  cmp     byte ptr [rcx+28h], 0
0x18000608a  jz      short loc_18000609C
0x18000608c  mov     byte ptr [rcx+28h], 0
0x180006090  call    cs:__imp_DeleteCriticalSection
0x180006097  nop     dword ptr [rax+rax+00h]
0x18000609c  mov     rbx, [rsp+28h+arg_0]
0x1800060a1  add     rsp, 20h
0x1800060a5  pop     rdi
0x1800060a6  retn
```
