# EtwpValidateTraceProperties(_EVENT_TRACE_PROPERTIES *,ulong *,_EVENT_FILTER_DESCRIPTOR * *,ulong *)

- ea: `0x1800098ec`
- end: `0x1800099b7`
- name: `?EtwpValidateTraceProperties@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAKPEAPEAU_EVENT_FILTER_DESCRIPTOR@@1@Z`
- size: `203`
- prototype: `unsigned int __fastcall(struct _EVENT_TRACE_PROPERTIES *, unsigned int *, struct _EVENT_FILTER_DESCRIPTOR **, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180009488`
- `0x1800098ec`

## pseudocode

```c
__int64 __fastcall EtwpValidateTraceProperties(
        struct _EVENT_TRACE_PROPERTIES *a1,
        unsigned int *a2,
        struct _EVENT_FILTER_DESCRIPTOR **a3,
        unsigned int *a4)
{
  ULONG LoggerNameOffset; // eax
  ULONG LogFileNameOffset; // eax
  struct _EVENT_FILTER_DESCRIPTOR *HistoricalContext; // rdi
  ULONG ProviderId; // ebx
  __int64 result; // rax

  *a3 = 0;
  *a2 = 0;
  if ( a1->Wnode.BufferSize >= 0x78 )
  {
    LoggerNameOffset = a1->LoggerNameOffset;
    if ( LoggerNameOffset && (LoggerNameOffset < 0x78 || LoggerNameOffset > a1->Wnode.BufferSize) )
      return 87;
    LogFileNameOffset = a1->LogFileNameOffset;
    if ( LogFileNameOffset )
    {
      if ( LogFileNameOffset < 0x78 || LogFileNameOffset > a1->Wnode.BufferSize )
        return 87;
    }
    if ( (a1->Wnode.Flags & 0x800000) == 0 )
    {
      *a4 = 120;
      return 0;
    }
    *a4 = 144;
    if ( a1->Wnode.BufferSize >= 0x90 )
    {
      HistoricalContext = (struct _EVENT_FILTER_DESCRIPTOR *)a1[1].Wnode.HistoricalContext;
      ProviderId = a1[1].Wnode.ProviderId;
      if ( (ProviderId == 0) != (HistoricalContext == 0) )
        return 87;
      if ( ProviderId && (a1->LogFileMode & 0x800) != 0 )
      {
        result = EtwpValidateFilterDescriptors(
                   1,
                   0,
                   ProviderId,
                   (struct _EVENT_FILTER_DESCRIPTOR *)a1[1].Wnode.HistoricalContext);
        if ( (_DWORD)result )
          return result;
        *a2 = ProviderId;
        *a3 = HistoricalContext;
      }
      return 0;
    }
  }
  return 24;
}

```

## disassembly

```asm
0x1800098ec  push    rbx
0x1800098ee  push    rsi
0x1800098ef  push    rdi
0x1800098f0  push    r14
0x1800098f2  sub     rsp, 28h
0x1800098f6  mov     r10, rcx
0x1800098f9  mov     qword ptr [r8], 0
0x180009900  mov     ecx, 78h ; 'x'
0x180009905  mov     dword ptr [rdx], 0
0x18000990b  mov     rsi, r8
0x18000990e  mov     r14, rdx
0x180009911  cmp     [r10], ecx
0x180009914  jb      loc_1800099A8
0x18000991a  mov     eax, [r10+74h]
0x18000991e  test    eax, eax
0x180009920  jz      short loc_18000992B
0x180009922  cmp     eax, ecx
0x180009924  jb      short loc_180009971
0x180009926  cmp     eax, [r10]
0x180009929  ja      short loc_180009971
0x18000992b  mov     eax, [r10+70h]
0x18000992f  test    eax, eax
0x180009931  jz      short loc_18000993C
0x180009933  cmp     eax, ecx
0x180009935  jb      short loc_180009971
0x180009937  cmp     eax, [r10]
0x18000993a  ja      short loc_180009971
0x18000993c  test    dword ptr [r10+2Ch], 800000h
0x180009944  jz      short loc_1800099A1
0x180009946  mov     eax, 90h
0x18000994b  mov     [r9], eax
0x18000994e  cmp     [r10], eax
0x180009951  jb      short loc_1800099A8
0x180009953  mov     rdi, [r10+80h]
0x18000995a  xor     ecx, ecx
0x18000995c  mov     ebx, [r10+7Ch]
0x180009960  test    rdi, rdi
0x180009963  setz    cl
0x180009966  xor     eax, eax
0x180009968  test    ebx, ebx
0x18000996a  setz    al
0x18000996d  cmp     eax, ecx
0x18000996f  jz      short loc_180009978
0x180009971  mov     eax, 57h ; 'W'
0x180009976  jmp     short loc_1800099AD
0x180009978  test    ebx, ebx
0x18000997a  jz      short loc_1800099A4
0x18000997c  test    dword ptr [r10+40h], 800h
0x180009984  jz      short loc_1800099A4
0x180009986  mov     r9, rdi; struct _EVENT_FILTER_DESCRIPTOR *
0x180009989  mov     r8d, ebx; unsigned int
0x18000998c  xor     edx, edx; unsigned int
0x18000998e  mov     cl, 1; unsigned __int8
0x180009990  call    ?EtwpValidateFilterDescriptors@@YAKEKKPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpValidateFilterDescriptors(uchar,ulong,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x180009995  test    eax, eax
0x180009997  jnz     short loc_1800099AD
0x180009999  mov     [r14], ebx
0x18000999c  mov     [rsi], rdi
0x18000999f  jmp     short loc_1800099A4
0x1800099a1  mov     [r9], ecx
0x1800099a4  xor     eax, eax
0x1800099a6  jmp     short loc_1800099AD
0x1800099a8  mov     eax, 18h
0x1800099ad  add     rsp, 28h
0x1800099b1  pop     r14
0x1800099b3  pop     rdi
0x1800099b4  pop     rsi
0x1800099b5  pop     rbx
0x1800099b6  retn
```
