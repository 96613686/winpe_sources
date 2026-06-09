# SaBlob_Create

- ea: `0x18001560c`
- end: `0x180015716`
- name: `SaBlob_Create`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180015310`
- `0x18001f4e0`

## callees

- `0x180004410`
- `0x18001560c`
- `0x180029a14`
- `0x180038104`
- `0x18003ae8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800156fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800156fc`
- `DNSAPI!DnsAddrArrayCreate` at `0x180015697`
- `DNSAPI!DnsAddrArrayCreate` at `0x180015697`
- `DNSAPI!DnsApiAllocZero` at `0x18001563f`
- `DNSAPI!DnsApiAllocZero` at `0x180015678`
- `DNSAPI!DnsApiAllocZero` at `0x18001563f`
- `DNSAPI!DnsApiAllocZero` at `0x180015678`

## pseudocode

```c
__int64 __fastcall SaBlob_Create(unsigned int a1)
{
  __int64 v2; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int *v4; // rax
  __int64 v5; // rax

  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_d(1025, 10, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, a1);
  v2 = DnsApiAllocZero(96);
  if ( v2 )
  {
    if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( !a1 )
      {
LABEL_14:
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 11, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids);
        return v2;
      }
      v4 = (unsigned int *)DnsApiAllocZero(((a1 - 1) << 6) + 96);
      *(_QWORD *)(v2 + 8) = v4;
      if ( v4 )
      {
        *v4 = a1;
        goto LABEL_14;
      }
    }
    else
    {
      if ( !a1 )
        goto LABEL_14;
      v5 = DnsAddrArrayCreate(a1);
      if ( v5 )
      {
        *(_QWORD *)(v2 + 8) = v5;
        goto LABEL_14;
      }
    }
  }
  SaBlob_Free(v2);
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 12, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids);
  SetLastError(0xEu);
  return 0;
}

```

## disassembly

```asm
0x18001560c  mov     [rsp+arg_0], rbx
0x180015611  push    rdi
0x180015612  sub     rsp, 20h
0x180015616  mov     ebx, ecx
0x180015618  test    byte ptr cs:xmmword_180063D60, 2
0x18001561f  jz      short loc_18001563A
0x180015621  mov     edx, 0Ah
0x180015626  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x18001562d  mov     ecx, 401h
0x180015632  mov     r9d, ebx
0x180015635  call    WPP_SF_d
0x18001563a  mov     ecx, 60h ; '`'
0x18001563f  call    cs:__imp_DnsApiAllocZero
0x180015646  nop     dword ptr [rax+rax+00h]
0x18001564b  mov     rdi, rax
0x18001564e  test    rax, rax
0x180015651  jz      short loc_1800156D0
0x180015653  mov     eax, cs:Feature_5977_1413__private_featureState
0x180015659  test    al, 10h
0x18001565b  jz      short loc_180015662
0x18001565d  and     eax, 1
0x180015660  jmp     short loc_180015667
0x180015662  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x180015667  test    eax, eax
0x180015669  jz      short loc_180015691
0x18001566b  test    ebx, ebx
0x18001566d  jz      short loc_1800156AC
0x18001566f  lea     ecx, [rbx-1]
0x180015672  shl     ecx, 6
0x180015675  add     ecx, 60h ; '`'
0x180015678  call    cs:__imp_DnsApiAllocZero
0x18001567f  nop     dword ptr [rax+rax+00h]
0x180015684  mov     [rdi+8], rax
0x180015688  test    rax, rax
0x18001568b  jz      short loc_1800156D0
0x18001568d  mov     [rax], ebx
0x18001568f  jmp     short loc_1800156AC
0x180015691  test    ebx, ebx
0x180015693  jz      short loc_1800156AC
0x180015695  mov     ecx, ebx
0x180015697  call    cs:__imp_DnsAddrArrayCreate
0x18001569e  nop     dword ptr [rax+rax+00h]
0x1800156a3  test    rax, rax
0x1800156a6  jz      short loc_1800156D0
0x1800156a8  mov     [rdi+8], rax
0x1800156ac  test    byte ptr cs:xmmword_180063D60, 2
0x1800156b3  jz      short loc_1800156CB
0x1800156b5  mov     edx, 0Bh
0x1800156ba  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800156c1  mov     ecx, 401h
0x1800156c6  call    WPP_SF_
0x1800156cb  mov     rax, rdi
0x1800156ce  jmp     short loc_18001570A
0x1800156d0  mov     rcx, rdi
0x1800156d3  call    SaBlob_Free
0x1800156d8  test    byte ptr cs:xmmword_180063D60, 2
0x1800156df  jz      short loc_1800156F7
0x1800156e1  mov     edx, 0Ch
0x1800156e6  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800156ed  mov     ecx, 401h
0x1800156f2  call    WPP_SF_
0x1800156f7  mov     ecx, 0Eh; dwErrCode
0x1800156fc  call    cs:__imp_SetLastError
0x180015703  nop     dword ptr [rax+rax+00h]
0x180015708  xor     eax, eax
0x18001570a  mov     rbx, [rsp+28h+arg_0]
0x18001570f  add     rsp, 20h
0x180015713  pop     rdi
0x180015714  retn
```
