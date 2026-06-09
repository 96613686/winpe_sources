# EtwpCopyLogHeader(_TRACE_LOGFILE_HEADER *,void *,ulong,ushort * *)

- ea: `0x180004768`
- end: `0x180004856`
- name: `?EtwpCopyLogHeader@@YAXPEAU_TRACE_LOGFILE_HEADER@@PEAXKPEAPEAG@Z`
- size: `238`
- prototype: `void __fastcall(struct _TRACE_LOGFILE_HEADER *, void *, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000501c`
- `0x1800052b4`

## pseudocode

```c
void __fastcall EtwpCopyLogHeader(struct _TRACE_LOGFILE_HEADER *a1, _DWORD *a2, __int64 a3, unsigned __int16 **a4)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned __int16 *v6; // rax

  v4 = a2[11];
  *(_OWORD *)&a1->BufferSize = *(_OWORD *)a2;
  v5 = (unsigned int)(2 * v4);
  v6 = (unsigned __int16 *)((char *)a2 + (unsigned int)(v5 + 264));
  *(_OWORD *)&a1->EndTime.LowPart = *((_OWORD *)a2 + 1);
  *a4 = v6;
  *(_OWORD *)&a1->LogFileMode = *((_OWORD *)a2 + 2);
  *(_QWORD *)&a1->EventsLost = *((_QWORD *)a2 + 6);
  *(_OWORD *)&a1->TimeZone.Bias = *(_OWORD *)((char *)a2 + v5 + 56);
  *(_OWORD *)&a1->TimeZone.StandardName[6] = *(_OWORD *)((char *)a2 + v5 + 72);
  *(_OWORD *)&a1->TimeZone.StandardName[14] = *(_OWORD *)((char *)a2 + v5 + 88);
  *(_OWORD *)&a1->TimeZone.StandardName[22] = *(_OWORD *)((char *)a2 + v5 + 104);
  *(_OWORD *)&a1->TimeZone.StandardName[30] = *(_OWORD *)((char *)a2 + v5 + 120);
  *(_OWORD *)&a1->TimeZone.StandardDate.wSecond = *(_OWORD *)((char *)a2 + v5 + 136);
  *(_OWORD *)&a1->TimeZone.DaylightName[4] = *(_OWORD *)((char *)a2 + v5 + 152);
  *(_OWORD *)&a1->TimeZone.DaylightName[12] = *(_OWORD *)((char *)a2 + v5 + 168);
  *(_OWORD *)&a1->TimeZone.DaylightName[20] = *(_OWORD *)((char *)a2 + v5 + 184);
  *(_OWORD *)&a1->TimeZone.DaylightName[28] = *(_OWORD *)((char *)a2 + v5 + 200);
  *(_OWORD *)&a1->TimeZone.DaylightDate.wHour = *(_OWORD *)((char *)a2 + v5 + 216);
  *(_OWORD *)&a1->BootTime.LowPart = *(_OWORD *)((char *)a2 + v5 + 232);
  *(_OWORD *)&a1->StartTime.LowPart = *(_OWORD *)((char *)a2 + v5 + 248);
  a1->LoggerName = v6;
}

```

## disassembly

```asm
0x180004768  mov     eax, [rdx+2Ch]
0x18000476b  movups  xmm0, xmmword ptr [rdx]
0x18000476e  movups  xmmword ptr [rcx], xmm0
0x180004771  lea     r8d, [rax+rax]
0x180004775  movups  xmm1, xmmword ptr [rdx+10h]
0x180004779  lea     eax, [r8+108h]
0x180004780  add     rax, rdx
0x180004783  movups  xmmword ptr [rcx+10h], xmm1
0x180004787  mov     [r9], rax
0x18000478a  movups  xmm0, xmmword ptr [rdx+20h]
0x18000478e  movups  xmmword ptr [rcx+20h], xmm0
0x180004792  movsd   xmm1, qword ptr [rdx+30h]
0x180004797  movsd   qword ptr [rcx+30h], xmm1
0x18000479c  movups  xmm0, xmmword ptr [r8+rdx+38h]
0x1800047a2  movups  xmmword ptr [rcx+48h], xmm0
0x1800047a6  movups  xmm1, xmmword ptr [r8+rdx+48h]
0x1800047ac  movups  xmmword ptr [rcx+58h], xmm1
0x1800047b0  movups  xmm0, xmmword ptr [r8+rdx+58h]
0x1800047b6  movups  xmmword ptr [rcx+68h], xmm0
0x1800047ba  movups  xmm1, xmmword ptr [r8+rdx+68h]
0x1800047c0  movups  xmmword ptr [rcx+78h], xmm1
0x1800047c4  movups  xmm0, xmmword ptr [r8+rdx+78h]
0x1800047ca  movups  xmmword ptr [rcx+88h], xmm0
0x1800047d1  movups  xmm1, xmmword ptr [r8+rdx+88h]
0x1800047da  movups  xmmword ptr [rcx+98h], xmm1
0x1800047e1  movups  xmm0, xmmword ptr [r8+rdx+98h]
0x1800047ea  movups  xmmword ptr [rcx+0A8h], xmm0
0x1800047f1  movups  xmm1, xmmword ptr [r8+rdx+0A8h]
0x1800047fa  movups  xmmword ptr [rcx+0B8h], xmm1
0x180004801  movups  xmm0, xmmword ptr [r8+rdx+0B8h]
0x18000480a  movups  xmmword ptr [rcx+0C8h], xmm0
0x180004811  movups  xmm1, xmmword ptr [r8+rdx+0C8h]
0x18000481a  movups  xmmword ptr [rcx+0D8h], xmm1
0x180004821  movups  xmm0, xmmword ptr [r8+rdx+0D8h]
0x18000482a  movups  xmmword ptr [rcx+0E8h], xmm0
0x180004831  movups  xmm1, xmmword ptr [r8+rdx+0E8h]
0x18000483a  movups  xmmword ptr [rcx+0F8h], xmm1
0x180004841  movups  xmm0, xmmword ptr [r8+rdx+0F8h]
0x18000484a  movups  xmmword ptr [rcx+108h], xmm0
0x180004851  mov     [rcx+38h], rax
0x180004855  retn
```
