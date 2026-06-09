# DuiTaskDlg::Initialize(HINSTANCE__ *)

- ea: `0x180002660`
- end: `0x1800026c1`
- name: `?Initialize@DuiTaskDlg@@UEAAJPEAUHINSTANCE__@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(DuiTaskDlg *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002f00`

## callees

- `0x180001254`
- `0x180002660`
- `0x18000ccde`

## pseudocode

```c
__int64 __fastcall DuiTaskDlg::Initialize(DuiTaskDlg *this, HINSTANCE a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rcx

  *((_QWORD *)this + 2) = a2;
  memset_0((char *)this + 32, 0, 0xA0u);
  v3 = operator new(0xB8u);
  if ( v3 )
  {
    v4 = *((_QWORD *)this + 2);
    *v3 = v4;
    v3[2] = v4;
    v3[1] = 0;
    v3[22] = 1;
  }
  *((_QWORD *)this + 3) = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180002660  push    rbx
0x180002662  sub     rsp, 20h
0x180002666  mov     [rcx+10h], rdx
0x18000266a  mov     rbx, rcx
0x18000266d  add     rcx, 20h ; ' '; void *
0x180002671  xor     edx, edx; Val
0x180002673  mov     r8d, 0A0h; Size
0x180002679  call    memset_0
0x18000267e  mov     ecx, 0B8h; Size
0x180002683  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002688  test    rax, rax
0x18000268b  jz      short loc_1800026AB
0x18000268d  mov     rcx, [rbx+10h]
0x180002691  mov     [rax], rcx
0x180002694  mov     [rax+10h], rcx
0x180002698  mov     qword ptr [rax+8], 0
0x1800026a0  mov     qword ptr [rax+0B0h], 1
0x1800026ab  mov     [rbx+18h], rax
0x1800026af  neg     rax
0x1800026b2  sbb     eax, eax
0x1800026b4  not     eax
0x1800026b6  and     eax, 8007000Eh
0x1800026bb  add     rsp, 20h
0x1800026bf  pop     rbx
0x1800026c0  retn
```
