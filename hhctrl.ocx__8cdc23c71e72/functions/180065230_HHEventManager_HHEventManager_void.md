# HHEventManager::HHEventManager(void)

- ea: `0x180065230`
- end: `0x1800652ac`
- name: `??0HHEventManager@@QEAA@XZ`
- size: `124`
- prototype: `HHEventManager *__fastcall(HHEventManager *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800015e0`
- `0x180017ce0`
- `0x180037594`
- `0x180069040`
- `0x18006a480`

## import_xrefs

- `ADVAPI32!RegisterEventSourceA` at `0x18006529a`
- `ADVAPI32!RegisterEventSourceA` at `0x18006529a`

## string_xrefs

- `0x180065236`: `https://go.microsoft.com/fwlink?LinkID=45833`
- `0x18006524b`: `https://go.microsoft.com/fwlink?LinkID=45837`
- `0x180065256`: `https://go.microsoft.com/fwlink?LinkID=45838`
- `0x180065261`: `https://go.microsoft.com/fwlink?LinkID=45839`
- `0x18006526c`: `https://go.microsoft.com/fwlink?LinkID=45840`
- `0x180065277`: `https://go.microsoft.com/fwlink?LinkID=45841`
- `0x180065282`: `https://go.microsoft.com/fwlink?LinkID=45842`
- `0x18006528d`: `https://go.microsoft.com/fwlink?LinkID=45843`

## pseudocode

```c
HHEventManager *__fastcall HHEventManager::HHEventManager(HHEventManager *this)
{
  *((_QWORD *)this + 1) = "https://go.microsoft.com/fwlink?LinkID=45833";
  *((_QWORD *)this + 2) = "https://go.microsoft.com/fwlink?LinkID=45837";
  *((_QWORD *)this + 3) = "https://go.microsoft.com/fwlink?LinkID=45838";
  *((_QWORD *)this + 4) = "https://go.microsoft.com/fwlink?LinkID=45839";
  *((_QWORD *)this + 5) = "https://go.microsoft.com/fwlink?LinkID=45840";
  *((_QWORD *)this + 6) = "https://go.microsoft.com/fwlink?LinkID=45841";
  *((_QWORD *)this + 7) = "https://go.microsoft.com/fwlink?LinkID=45842";
  *((_QWORD *)this + 8) = "https://go.microsoft.com/fwlink?LinkID=45843";
  *(_QWORD *)this = RegisterEventSourceA(0, "HHCTRL");
  return this;
}

```

## disassembly

```asm
0x180065230  push    rbx
0x180065232  sub     rsp, 20h
0x180065236  lea     rax, aHttpsGoMicroso_5; "https://go.microsoft.com/fwlink?LinkID="...
0x18006523d  mov     rbx, rcx
0x180065240  mov     [rcx+8], rax
0x180065244  lea     rdx, SourceName; "HHCTRL"
0x18006524b  lea     rax, aHttpsGoMicroso_0; "https://go.microsoft.com/fwlink?LinkID="...
0x180065252  mov     [rcx+10h], rax
0x180065256  lea     rax, aHttpsGoMicroso_1; "https://go.microsoft.com/fwlink?LinkID="...
0x18006525d  mov     [rcx+18h], rax
0x180065261  lea     rax, aHttpsGoMicroso_6; "https://go.microsoft.com/fwlink?LinkID="...
0x180065268  mov     [rcx+20h], rax
0x18006526c  lea     rax, aHttpsGoMicroso_4; "https://go.microsoft.com/fwlink?LinkID="...
0x180065273  mov     [rcx+28h], rax
0x180065277  lea     rax, aHttpsGoMicroso_3; "https://go.microsoft.com/fwlink?LinkID="...
0x18006527e  mov     [rcx+30h], rax
0x180065282  lea     rax, aHttpsGoMicroso_2; "https://go.microsoft.com/fwlink?LinkID="...
0x180065289  mov     [rcx+38h], rax
0x18006528d  lea     rax, aHttpsGoMicroso; "https://go.microsoft.com/fwlink?LinkID="...
0x180065294  mov     [rcx+40h], rax
0x180065298  xor     ecx, ecx; lpUNCServerName
0x18006529a  call    cs:__imp_RegisterEventSourceA
0x1800652a0  mov     [rbx], rax
0x1800652a3  mov     rax, rbx
0x1800652a6  add     rsp, 20h
0x1800652aa  pop     rbx
0x1800652ab  retn
```
