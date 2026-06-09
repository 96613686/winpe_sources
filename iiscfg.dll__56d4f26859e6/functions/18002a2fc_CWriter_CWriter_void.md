# CWriter::~CWriter(void)

- ea: `0x18002a2fc`
- end: `0x18002a395`
- name: `??1CWriter@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(CWriter *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023e00`
- `0x18002ef11`

## callees

- `0x18002a2fc`
- `0x18002a39c`
- `0x18002a664`
- `0x180030010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002a331`
- `KERNEL32!CloseHandle` at `0x18002a331`
- `ole32!CoTaskMemFree` at `0x18002a30d`
- `ole32!CoTaskMemFree` at `0x18002a30d`

## pseudocode

```c
void __fastcall CWriter::~CWriter(CWriter *this)
{
  void *v2; // rcx
  char *v3; // rcx
  unsigned int v4; // edx
  __int64 v5; // rcx
  CWriterGlobalHelper *v6; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)this = 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v3 = (char *)*((_QWORD *)this + 8199);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
  }
  *((_QWORD *)this + 8199) = -1;
  CWriter::FreeSecurityRelatedMembers(this);
  v5 = *((_QWORD *)this + 8201);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 8201) = 0;
  }
  if ( *((_DWORD *)this + 3) )
  {
    v6 = (CWriterGlobalHelper *)*((_QWORD *)this + 8200);
    if ( v6 )
      CWriterGlobalHelper::`scalar deleting destructor'(v6, v4);
    *((_QWORD *)this + 8200) = 0;
  }
}

```

## disassembly

```asm
0x18002a2fc  push    rbx
0x18002a2fe  sub     rsp, 20h
0x18002a302  mov     rbx, rcx
0x18002a305  mov     rcx, [rcx]; pv
0x18002a308  test    rcx, rcx
0x18002a30b  jz      short loc_18002A31A
0x18002a30d  call    cs:__imp_CoTaskMemFree
0x18002a313  mov     qword ptr [rbx], 0
0x18002a31a  cmp     dword ptr [rbx+8], 0
0x18002a31e  jz      short loc_18002A337
0x18002a320  mov     rcx, [rbx+10038h]; hObject
0x18002a327  lea     rax, [rcx-1]
0x18002a32b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a32f  ja      short loc_18002A337
0x18002a331  call    cs:__imp_CloseHandle
0x18002a337  mov     rcx, rbx; this
0x18002a33a  mov     qword ptr [rbx+10038h], 0FFFFFFFFFFFFFFFFh
0x18002a345  call    ?FreeSecurityRelatedMembers@CWriter@@AEAAXXZ; CWriter::FreeSecurityRelatedMembers(void)
0x18002a34a  mov     rcx, [rbx+10048h]
0x18002a351  test    rcx, rcx
0x18002a354  jz      short loc_18002A36D
0x18002a356  mov     rax, [rcx]
0x18002a359  mov     rax, [rax+10h]
0x18002a35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a362  mov     qword ptr [rbx+10048h], 0
0x18002a36d  cmp     dword ptr [rbx+0Ch], 0
0x18002a371  jz      short loc_18002A38F
0x18002a373  mov     rcx, [rbx+10040h]; this
0x18002a37a  test    rcx, rcx
0x18002a37d  jz      short loc_18002A384
0x18002a37f  call    ??_GCWriterGlobalHelper@@QEAAPEAXI@Z; CWriterGlobalHelper::`scalar deleting destructor'(uint)
0x18002a384  mov     qword ptr [rbx+10040h], 0
0x18002a38f  add     rsp, 20h
0x18002a393  pop     rbx
0x18002a394  retn
```
