# JsonObject::JsonObject(void)

- ea: `0x14001c7ac`
- end: `0x14001c80c`
- name: `??0JsonObject@@QEAA@XZ`
- size: `96`
- prototype: `JsonObject *__fastcall(JsonObject *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400239a4`
- `0x140023b80`
- `0x140023e64`
- `0x140029854`
- `0x14002a154`

## callees

- `0x1400017d4`

## pseudocode

```c
JsonObject *__fastcall JsonObject::JsonObject(JsonObject *this)
{
  _QWORD *v2; // rax

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &JsonObject::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v2 = operator new(0x48u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *((_QWORD *)this + 2) = v2;
  return this;
}

```

## disassembly

```asm
0x14001c7ac  mov     [rsp+arg_10], rbx
0x14001c7b1  mov     [rsp+arg_0], rcx
0x14001c7b6  push    rdi
0x14001c7b7  sub     rsp, 20h
0x14001c7bb  mov     rdi, rcx
0x14001c7be  mov     dword ptr [rcx+8], 1
0x14001c7c5  lea     rax, ??_7JsonObject@@6B@; const JsonObject::`vftable'
0x14001c7cc  mov     [rcx], rax
0x14001c7cf  mov     qword ptr [rcx+10h], 0
0x14001c7d7  mov     qword ptr [rcx+18h], 0
0x14001c7df  mov     ecx, 48h ; 'H'; Size
0x14001c7e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001c7e9  mov     [rax], rax
0x14001c7ec  mov     [rax+8], rax
0x14001c7f0  mov     [rax+10h], rax
0x14001c7f4  mov     word ptr [rax+18h], 101h
0x14001c7fa  mov     [rdi+10h], rax
0x14001c7fe  mov     rax, rdi
0x14001c801  mov     rbx, [rsp+28h+arg_10]
0x14001c806  add     rsp, 20h
0x14001c80a  pop     rdi
0x14001c80b  retn
```
