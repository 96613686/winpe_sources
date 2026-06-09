# CWorkerThread::CWorkerThread(void)

- ea: `0x18000bcc4`
- end: `0x18000bd38`
- name: `??0CWorkerThread@@QEAA@XZ`
- size: `116`
- prototype: `CWorkerThread *__fastcall(CWorkerThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f00`
- `0x180007330`

## callees

- `0x1800092b0`

## pseudocode

```c
CWorkerThread *__fastcall CWorkerThread::CWorkerThread(CWorkerThread *this)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)this + 3);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 1;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 255;
  *((_DWORD *)this + 23) = 0;
  *(_QWORD *)((char *)this + 84) = 0;
  return this;
}

```

## disassembly

```asm
0x18000bcc4  push    rbx
0x18000bcc6  sub     rsp, 20h
0x18000bcca  mov     qword ptr [rcx], 0
0x18000bcd1  mov     rbx, rcx
0x18000bcd4  mov     qword ptr [rcx+8], 0
0x18000bcdc  mov     qword ptr [rcx+10h], 0
0x18000bce4  add     rcx, 18h
0x18000bce8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000bced  xor     eax, eax
0x18000bcef  mov     qword ptr [rbx+20h], 0
0x18000bcf7  mov     qword ptr [rbx+28h], 0
0x18000bcff  mov     dword ptr [rbx+30h], 1
0x18000bd06  mov     qword ptr [rbx+38h], 0
0x18000bd0e  mov     dword ptr [rbx+40h], 0
0x18000bd15  mov     qword ptr [rbx+48h], 0
0x18000bd1d  mov     dword ptr [rbx+50h], 0FFh
0x18000bd24  mov     dword ptr [rbx+5Ch], 0
0x18000bd2b  mov     [rbx+54h], rax
0x18000bd2f  mov     rax, rbx
0x18000bd32  add     rsp, 20h
0x18000bd36  pop     rbx
0x18000bd37  retn
```
