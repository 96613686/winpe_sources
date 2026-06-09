# EtwpCopyInfoToProperties(_WMI_LOGGER_INFORMATION *,_EVENT_TRACE_PROPERTIES *)

- ea: `0x180013138`
- end: `0x1800131e4`
- name: `?EtwpCopyInfoToProperties@@YAXPEAU_WMI_LOGGER_INFORMATION@@PEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `172`
- prototype: `void __fastcall(struct _WMI_LOGGER_INFORMATION *, struct _EVENT_TRACE_PROPERTIES *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180013138`

## pseudocode

```c
void __fastcall EtwpCopyInfoToProperties(struct _WMI_LOGGER_INFORMATION *a1, struct _EVENT_TRACE_PROPERTIES *a2)
{
  ULONG BufferSize; // eax
  ULONG Flags; // r8d
  ULONG v4; // eax

  BufferSize = a2->Wnode.BufferSize;
  Flags = a2->Wnode.Flags;
  *(_OWORD *)&a2->Wnode.BufferSize = *(_OWORD *)a1;
  *(_OWORD *)&a2->Wnode.CountLost = *((_OWORD *)a1 + 1);
  *(_OWORD *)a2->Wnode.Guid.Data4 = *((_OWORD *)a1 + 2);
  a2->Wnode.BufferSize = BufferSize;
  a2->BufferSize = *((_DWORD *)a1 + 12);
  a2->MinimumBuffers = *((_DWORD *)a1 + 13);
  a2->MaximumBuffers = *((_DWORD *)a1 + 14);
  a2->MaximumFileSize = *((_DWORD *)a1 + 15);
  a2->LogFileMode = *((_DWORD *)a1 + 16);
  a2->FlushTimer = *((_DWORD *)a1 + 17);
  a2->EnableFlags = *((_DWORD *)a1 + 18);
  a2->AgeLimit = *((_DWORD *)a1 + 19);
  a2->NumberOfBuffers = *((_DWORD *)a1 + 24);
  a2->FreeBuffers = *((_DWORD *)a1 + 25);
  a2->EventsLost = *((_DWORD *)a1 + 26);
  a2->BuffersWritten = *((_DWORD *)a1 + 27);
  a2->LogBuffersLost = *((_DWORD *)a1 + 28);
  a2->RealTimeBuffersLost = *((_DWORD *)a1 + 29);
  a2->LoggerThreadId = (HANDLE)*((_QWORD *)a1 + 15);
  v4 = a2->Wnode.Flags;
  if ( (Flags & 0x800000) != 0 )
  {
    a2->Wnode.Flags = v4 | 0x800000;
    a2[1].Wnode.TimeStamp.QuadPart = *((_QWORD *)a1 + 10);
  }
  else
  {
    a2->Wnode.Flags = v4 & 0xFF7FFFFF;
  }
  a2->Wnode.ProviderId = *((_DWORD *)a1 + 40);
}

```

## disassembly

```asm
0x180013138  movups  xmm0, xmmword ptr [rcx]
0x18001313b  mov     eax, [rdx]
0x18001313d  mov     r9d, 800000h
0x180013143  mov     r8d, [rdx+2Ch]
0x180013147  movups  xmmword ptr [rdx], xmm0
0x18001314a  movups  xmm1, xmmword ptr [rcx+10h]
0x18001314e  movups  xmmword ptr [rdx+10h], xmm1
0x180013152  movups  xmm0, xmmword ptr [rcx+20h]
0x180013156  movups  xmmword ptr [rdx+20h], xmm0
0x18001315a  mov     [rdx], eax
0x18001315c  mov     eax, [rcx+30h]
0x18001315f  mov     [rdx+30h], eax
0x180013162  mov     eax, [rcx+34h]
0x180013165  mov     [rdx+34h], eax
0x180013168  mov     eax, [rcx+38h]
0x18001316b  mov     [rdx+38h], eax
0x18001316e  mov     eax, [rcx+3Ch]
0x180013171  mov     [rdx+3Ch], eax
0x180013174  mov     eax, [rcx+40h]
0x180013177  mov     [rdx+40h], eax
0x18001317a  mov     eax, [rcx+44h]
0x18001317d  mov     [rdx+44h], eax
0x180013180  mov     eax, [rcx+48h]
0x180013183  mov     [rdx+48h], eax
0x180013186  mov     eax, [rcx+4Ch]
0x180013189  mov     [rdx+4Ch], eax
0x18001318c  mov     eax, [rcx+60h]
0x18001318f  mov     [rdx+50h], eax
0x180013192  mov     eax, [rcx+64h]
0x180013195  mov     [rdx+54h], eax
0x180013198  mov     eax, [rcx+68h]
0x18001319b  mov     [rdx+58h], eax
0x18001319e  mov     eax, [rcx+6Ch]
0x1800131a1  mov     [rdx+5Ch], eax
0x1800131a4  mov     eax, [rcx+70h]
0x1800131a7  mov     [rdx+60h], eax
0x1800131aa  mov     eax, [rcx+74h]
0x1800131ad  mov     [rdx+64h], eax
0x1800131b0  mov     rax, [rcx+78h]
0x1800131b4  mov     [rdx+68h], rax
0x1800131b8  mov     eax, [rdx+2Ch]
0x1800131bb  test    r9d, r8d
0x1800131be  jz      short loc_1800131D3
0x1800131c0  or      eax, r9d
0x1800131c3  mov     [rdx+2Ch], eax
0x1800131c6  mov     rax, [rcx+50h]
0x1800131ca  mov     [rdx+88h], rax
0x1800131d1  jmp     short loc_1800131DA
0x1800131d3  btr     eax, 17h
0x1800131d7  mov     [rdx+2Ch], eax
0x1800131da  mov     eax, [rcx+0A0h]
0x1800131e0  mov     [rdx+4], eax
0x1800131e3  retn
```
