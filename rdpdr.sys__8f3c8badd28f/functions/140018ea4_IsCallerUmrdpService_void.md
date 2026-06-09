# IsCallerUmrdpService(void)

- ea: `0x140018ea4`
- end: `0x140018f28`
- name: `?IsCallerUmrdpService@@YAHXZ`
- size: `132`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x14002acc0`

## callees

- `0x140001e30`
- `0x1400023f4`
- `0x140003188`
- `0x140018ea4`
- `0x14002a4f8`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140018eb3`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140018eb3`

## pseudocode

```c
void *IsCallerUmrdpService(void)
{
  ULONG v0; // eax
  void *result; // rax
  void *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4[10]; // [rsp+20h] [rbp-28h] BYREF

  v0 = RtlLengthRequiredSid(6u);
  result = operator new(v0, 0x100u);
  v2 = result;
  if ( result )
  {
    v4[0] = 2014626298;
    v4[1] = 1656748749;
    v4[2] = -447485480;
    v4[3] = 918933055;
    v4[4] = -1825628840;
    InitializeServiceSid(result, v4);
    v3 = DrCheckCurrentProcessForServiceSid(v2);
    operator delete(v2);
    return (void *)v3;
  }
  return result;
}

```

## disassembly

```asm
0x140018ea4  mov     [rsp+arg_0], rbx
0x140018ea9  push    rdi
0x140018eaa  sub     rsp, 40h
0x140018eae  mov     ecx, 6; SubAuthorityCount
0x140018eb3  call    cs:__imp_RtlLengthRequiredSid
0x140018eba  nop     dword ptr [rax+rax+00h]
0x140018ebf  mov     ecx, eax; unsigned __int64
0x140018ec1  mov     edx, 100h; unsigned __int64
0x140018ec6  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140018ecb  mov     rdi, rax
0x140018ece  test    rax, rax
0x140018ed1  jz      short loc_140018F1C
0x140018ed3  lea     rdx, [rsp+48h+var_28]; unsigned int *
0x140018ed8  mov     [rsp+48h+var_28], 7814C1FAh
0x140018ee0  mov     rcx, rdi; Sid
0x140018ee3  mov     [rsp+48h+var_24], 62BFFACDh
0x140018eeb  mov     [rsp+48h+var_20], 0E553E9D8h
0x140018ef3  mov     [rsp+48h+var_1C], 36C5CE3Fh
0x140018efb  mov     [rsp+48h+var_18], 932F1D58h
0x140018f03  call    ?InitializeServiceSid@@YAXPEAXQEAK@Z; InitializeServiceSid(void *,ulong * const)
0x140018f08  mov     rcx, rdi; void *
0x140018f0b  call    ?DrCheckCurrentProcessForServiceSid@@YAHPEAX@Z; DrCheckCurrentProcessForServiceSid(void *)
0x140018f10  mov     rcx, rdi; void *
0x140018f13  mov     ebx, eax
0x140018f15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140018f1a  mov     eax, ebx
0x140018f1c  mov     rbx, [rsp+48h+arg_0]
0x140018f21  add     rsp, 40h
0x140018f25  pop     rdi
0x140018f26  retn
```
