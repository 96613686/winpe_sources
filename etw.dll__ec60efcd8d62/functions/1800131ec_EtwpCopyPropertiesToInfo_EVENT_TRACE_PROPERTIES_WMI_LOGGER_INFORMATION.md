# EtwpCopyPropertiesToInfo(_EVENT_TRACE_PROPERTIES *,_WMI_LOGGER_INFORMATION *)

- ea: `0x1800131ec`
- end: `0x18001327e`
- name: `?EtwpCopyPropertiesToInfo@@YAXPEAU_EVENT_TRACE_PROPERTIES@@PEAU_WMI_LOGGER_INFORMATION@@@Z`
- size: `146`
- prototype: `void __fastcall(struct _EVENT_TRACE_PROPERTIES *, struct _WMI_LOGGER_INFORMATION *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x1800131ec`

## pseudocode

```c
void __fastcall EtwpCopyPropertiesToInfo(struct _EVENT_TRACE_PROPERTIES *a1, struct _WMI_LOGGER_INFORMATION *a2)
{
  int v2; // eax
  bool v3; // zf
  _QWORD *v4; // rax
  HANDLE KernelHandle; // rdx

  v2 = *(_DWORD *)a2;
  *(_OWORD *)a2 = *(_OWORD *)&a1->Wnode.BufferSize;
  *((_OWORD *)a2 + 1) = *(_OWORD *)&a1->Wnode.CountLost;
  *((_OWORD *)a2 + 2) = *(_OWORD *)a1->Wnode.Guid.Data4;
  v3 = (*((_DWORD *)a2 + 11) & 0x800000) == 0;
  *(_DWORD *)a2 = v2;
  *((_DWORD *)a2 + 12) = a1->BufferSize;
  *((_DWORD *)a2 + 13) = a1->MinimumBuffers;
  *((_DWORD *)a2 + 14) = a1->MaximumBuffers;
  *((_DWORD *)a2 + 15) = a1->MaximumFileSize;
  *((_DWORD *)a2 + 16) = a1->LogFileMode;
  *((_DWORD *)a2 + 17) = a1->FlushTimer;
  *((_DWORD *)a2 + 18) = a1->EnableFlags;
  *((_DWORD *)a2 + 19) = a1->AgeLimit;
  *((_DWORD *)a2 + 24) = a1->NumberOfBuffers;
  *((_DWORD *)a2 + 25) = a1->FreeBuffers;
  *((_DWORD *)a2 + 26) = a1->EventsLost;
  *((_DWORD *)a2 + 27) = a1->BuffersWritten;
  *((_DWORD *)a2 + 28) = a1->LogBuffersLost;
  *((_DWORD *)a2 + 29) = a1->RealTimeBuffersLost;
  *((_QWORD *)a2 + 15) = a1->LoggerThreadId;
  v4 = (_QWORD *)((char *)a2 + 80);
  if ( v3 )
    KernelHandle = 0;
  else
    KernelHandle = a1[1].Wnode.KernelHandle;
  *v4 = KernelHandle;
}

```

## disassembly

```asm
0x1800131ec  movups  xmm0, xmmword ptr [rcx]
0x1800131ef  mov     eax, [rdx]
0x1800131f1  movups  xmmword ptr [rdx], xmm0
0x1800131f4  movups  xmm1, xmmword ptr [rcx+10h]
0x1800131f8  movups  xmmword ptr [rdx+10h], xmm1
0x1800131fc  movups  xmm0, xmmword ptr [rcx+20h]
0x180013200  movups  xmmword ptr [rdx+20h], xmm0
0x180013204  test    dword ptr [rdx+2Ch], 800000h
0x18001320b  mov     [rdx], eax
0x18001320d  mov     eax, [rcx+30h]
0x180013210  mov     [rdx+30h], eax
0x180013213  mov     eax, [rcx+34h]
0x180013216  mov     [rdx+34h], eax
0x180013219  mov     eax, [rcx+38h]
0x18001321c  mov     [rdx+38h], eax
0x18001321f  mov     eax, [rcx+3Ch]
0x180013222  mov     [rdx+3Ch], eax
0x180013225  mov     eax, [rcx+40h]
0x180013228  mov     [rdx+40h], eax
0x18001322b  mov     eax, [rcx+44h]
0x18001322e  mov     [rdx+44h], eax
0x180013231  mov     eax, [rcx+48h]
0x180013234  mov     [rdx+48h], eax
0x180013237  mov     eax, [rcx+4Ch]
0x18001323a  mov     [rdx+4Ch], eax
0x18001323d  mov     eax, [rcx+50h]
0x180013240  mov     [rdx+60h], eax
0x180013243  mov     eax, [rcx+54h]
0x180013246  mov     [rdx+64h], eax
0x180013249  mov     eax, [rcx+58h]
0x18001324c  mov     [rdx+68h], eax
0x18001324f  mov     eax, [rcx+5Ch]
0x180013252  mov     [rdx+6Ch], eax
0x180013255  mov     eax, [rcx+60h]
0x180013258  mov     [rdx+70h], eax
0x18001325b  mov     eax, [rcx+64h]
0x18001325e  mov     [rdx+74h], eax
0x180013261  mov     rax, [rcx+68h]
0x180013265  mov     [rdx+78h], rax
0x180013269  lea     rax, [rdx+50h]
0x18001326d  jz      short loc_180013278
0x18001326f  mov     rdx, [rcx+88h]
0x180013276  jmp     short loc_18001327A
0x180013278  xor     edx, edx
0x18001327a  mov     [rax], rdx
0x18001327d  retn
```
