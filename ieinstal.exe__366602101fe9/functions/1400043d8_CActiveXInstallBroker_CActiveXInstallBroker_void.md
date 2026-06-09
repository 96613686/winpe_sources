# CActiveXInstallBroker::CActiveXInstallBroker(void)

- ea: `0x1400043d8`
- end: `0x140004434`
- name: `??0CActiveXInstallBroker@@QEAA@XZ`
- size: `92`
- prototype: `CActiveXInstallBroker *__fastcall(CActiveXInstallBroker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007e20`
- `0x140007ed0`

## callees

- `0x14000443c`

## pseudocode

```c
CActiveXInstallBroker *__fastcall CActiveXInstallBroker::CActiveXInstallBroker(CActiveXInstallBroker *this)
{
  CLock::CLock(this);
  *((_DWORD *)this + 36) = 1;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_BYTE *)this + 160) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 12) = 0;
  return this;
}

```

## disassembly

```asm
0x1400043d8  push    rbx
0x1400043da  sub     rsp, 20h
0x1400043de  mov     rbx, rcx
0x1400043e1  call    ??0CLock@@QEAA@XZ; CLock::CLock(void)
0x1400043e6  xor     eax, eax
0x1400043e8  mov     dword ptr [rbx+90h], 1
0x1400043f2  mov     [rbx+88h], eax
0x1400043f8  mov     [rbx+68h], rax
0x1400043fc  mov     [rbx+70h], rax
0x140004400  mov     [rbx+38h], rax
0x140004404  mov     [rbx+40h], rax
0x140004408  mov     [rbx+48h], rax
0x14000440c  mov     [rbx+50h], rax
0x140004410  mov     [rbx+0A0h], al
0x140004416  mov     [rbx+78h], eax
0x140004419  mov     [rbx+80h], rax
0x140004420  mov     [rbx+98h], rax
0x140004427  mov     [rbx+30h], eax
0x14000442a  mov     rax, rbx
0x14000442d  add     rsp, 20h
0x140004431  pop     rbx
0x140004432  retn
```
