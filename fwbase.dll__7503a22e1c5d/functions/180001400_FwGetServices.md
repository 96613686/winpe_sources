# FwGetServices

- ea: `0x180001400`
- end: `0x1800014c9`
- name: `FwGetServices`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180001400`
- `0x1800014d0`
- `0x180001600`
- `0x180001720`
- `0x1800028e0`
- `0x1800047e0`

## string_xrefs

- `0x180001490`: `FwGetServices`
- `0x1800014ac`: `FwGetServices`
- `0x180001425`: `Services`

## pseudocode

```c
__int64 __fastcall FwGetServices(HKEY a1, __int64 a2)
{
  int ServiceSettings; // eax
  int v4; // ebx
  unsigned int i; // esi
  unsigned __int64 v6; // rdi
  __int64 Service; // rax
  int v9; // [rsp+60h] [rbp+18h] BYREF
  HKEY v10; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v9 = 0;
  ServiceSettings = FwRegOpenKey(a1, L"Services", 1u, &v10, &v9);
  v4 = ServiceSettings;
  if ( ServiceSettings < 0 )
  {
LABEL_7:
    FwReportReturnError("FwGetServices", (unsigned int)ServiceSettings);
  }
  else if ( v9 )
  {
    for ( i = 0; i < *(_DWORD *)a2; ++i )
    {
      v6 = ((unsigned __int64)i << 6) + *(_QWORD *)(a2 + 8);
      Service = FwGetService(*(unsigned int *)(v6 + 8));
      ServiceSettings = FwGetServiceSettings(
                          v10,
                          *(const unsigned __int16 **)(Service + 8),
                          (enum ICF_BOOL_ *)(v6 + 16),
                          (struct ICF_AUTHBYPASS_SUBNETS_ *)(v6 + 24));
      v4 = ServiceSettings;
      if ( ServiceSettings < 0 )
        goto LABEL_7;
    }
  }
  FwRegCloseKey(v10);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwGetServices", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001400  mov     r11, rsp
0x180001403  mov     [r11+8], rbx
0x180001407  push    rbp
0x180001408  push    rsi
0x180001409  push    rdi
0x18000140a  sub     rsp, 30h
0x18000140e  mov     rbp, rdx
0x180001411  mov     qword ptr [r11+20h], 0
0x180001419  lea     rax, [r11+18h]
0x18000141d  mov     [rsp+48h+arg_10], 0
0x180001425  lea     rdx, aServices; "Services"
0x18000142c  mov     [r11-28h], rax
0x180001430  lea     r9, [r11+20h]
0x180001434  mov     r8d, 1; samDesired
0x18000143a  call    FwRegOpenKey
0x18000143f  mov     ebx, eax
0x180001441  test    eax, eax
0x180001443  js      short loc_18000148E
0x180001445  cmp     [rsp+48h+arg_10], 0
0x18000144a  jz      short loc_18000149C
0x18000144c  xor     esi, esi
0x18000144e  cmp     esi, [rbp+0]
0x180001451  jnb     short loc_18000149C
0x180001453  mov     rcx, [rbp+8]
0x180001457  mov     eax, esi
0x180001459  shl     rax, 6
0x18000145d  lea     rbx, [rax+rcx]
0x180001461  lea     rdi, [rax+rcx]
0x180001465  mov     ecx, [rax+rcx+8]
0x180001469  call    FwGetService
0x18000146e  mov     rcx, [rsp+48h+arg_18]; HKEY
0x180001473  lea     r9, [rbx+18h]; struct ICF_AUTHBYPASS_SUBNETS_ *
0x180001477  lea     r8, [rdi+10h]; enum ICF_BOOL_ *
0x18000147b  mov     rdx, [rax+8]; unsigned __int16 *
0x18000147f  call    ?FwGetServiceSettings@@YAJPEAUHKEY__@@PEBGPEAW4ICF_BOOL_@@PEAUICF_AUTHBYPASS_SUBNETS_@@@Z; FwGetServiceSettings(HKEY__ *,ushort const *,ICF_BOOL_ *,ICF_AUTHBYPASS_SUBNETS_ *)
0x180001484  mov     ebx, eax
0x180001486  test    eax, eax
0x180001488  js      short loc_18000148E
0x18000148a  inc     esi
0x18000148c  jmp     short loc_18000144E
0x18000148e  mov     edx, eax
0x180001490  lea     rcx, aFwgetservices_0; "FwGetServices"
0x180001497  call    FwReportReturnError
0x18000149c  mov     rcx, [rsp+48h+arg_18]
0x1800014a1  call    FwRegCloseKey
0x1800014a6  test    ebx, ebx
0x1800014a8  jns     short loc_1800014BA
0x1800014aa  mov     edx, ebx
0x1800014ac  lea     rcx, aFwgetservices_0; "FwGetServices"
0x1800014b3  call    FwReportReturnError
0x1800014b8  mov     ebx, eax
0x1800014ba  mov     eax, ebx
0x1800014bc  mov     rbx, [rsp+48h+arg_0]
0x1800014c1  add     rsp, 30h
0x1800014c5  pop     rdi
0x1800014c6  pop     rsi
0x1800014c7  pop     rbp
0x1800014c8  retn
```
