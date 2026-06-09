# PrjfFreeEnumerationResultBuffer

- ea: `0x14003a644`
- end: `0x14003a6b7`
- name: `PrjfFreeEnumerationResultBuffer`
- size: `115`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006938`
- `0x140028760`

## callees

- `0x14000b1d0`
- `0x14003a644`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a6a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a6a5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a692`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a692`

## pseudocode

```c
void __fastcall PrjfFreeEnumerationResultBuffer(PVOID Entry, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID v4; // rdx
  struct _PAGED_LOOKASIDE_LIST *v5; // rcx

  if ( Entry )
  {
    if ( (unsigned int)a2 > 0x27C )
    {
      if ( (unsigned int)a2 > 0x1014 )
      {
        if ( (unsigned int)a2 > 0x10014 )
        {
          ExFreePoolWithTag(Entry, 0x6E654A50u);
          return;
        }
        v4 = Entry;
        v5 = &stru_14001AA40;
      }
      else
      {
        v4 = Entry;
        v5 = &stru_14001A9C0;
      }
    }
    else
    {
      v4 = Entry;
      v5 = &stru_14001A940;
    }
    ExFreeToPagedLookasideList(v5, v4);
    return;
  }
  if ( (_DWORD)a2 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(0, a2, a3, a4);
}

```

## disassembly

```asm
0x14003a644  sub     rsp, 28h
0x14003a648  test    rcx, rcx
0x14003a64b  jnz     short loc_14003A658
0x14003a64d  test    edx, edx
0x14003a64f  jz      short loc_14003A6B1
0x14003a651  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003a656  jmp     short loc_14003A6B1
0x14003a658  cmp     edx, 27Ch
0x14003a65e  ja      short loc_14003A66C
0x14003a660  mov     rdx, rcx
0x14003a663  lea     rcx, stru_14001A940
0x14003a66a  jmp     short loc_14003A692
0x14003a66c  cmp     edx, 1014h
0x14003a672  ja      short loc_14003A680
0x14003a674  mov     rdx, rcx
0x14003a677  lea     rcx, stru_14001A9C0
0x14003a67e  jmp     short loc_14003A692
0x14003a680  cmp     edx, 10014h
0x14003a686  ja      short loc_14003A6A0
0x14003a688  mov     rdx, rcx; Entry
0x14003a68b  lea     rcx, stru_14001AA40; Lookaside
0x14003a692  call    cs:__imp_ExFreeToPagedLookasideList
0x14003a699  nop     dword ptr [rax+rax+00h]
0x14003a69e  jmp     short loc_14003A6B1
0x14003a6a0  mov     edx, 6E654A50h; Tag
0x14003a6a5  call    cs:__imp_ExFreePoolWithTag
0x14003a6ac  nop     dword ptr [rax+rax+00h]
0x14003a6b1  add     rsp, 28h
0x14003a6b5  retn
```
