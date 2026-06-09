# CPacket::CloneCopy(ACPoolType,int)

- ea: `0x140014980`
- end: `0x140014a52`
- name: `?CloneCopy@CPacket@@AEBAPEAV1@W4ACPoolType@@H@Z`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140014948`
- `0x1400184cc`

## callees

- `0x140001cb0`
- `0x140009a04`
- `0x14000a1d4`
- `0x140012d34`
- `0x140012d8c`
- `0x140014980`
- `0x1400152d0`
- `0x140024cc0`

## pseudocode

```c
CQEntry *__fastcall CPacket::CloneCopy(CQEntry *a1, int a2, int a3)
{
  struct _KPROCESS *v6; // rcx
  struct _KPROCESS *v8; // rsi
  struct CPacketBuffer *v9; // rbp
  __int64 v10; // r14
  __int64 v11; // rdx
  unsigned int v12; // r8d
  struct CPacketBuffer *v13; // rax
  _QWORD *v14; // rbx
  CQEntry *v15; // [rsp+70h] [rbp+8h] BYREF

  v6 = *(struct _KPROCESS **)(*(_QWORD *)(*((_QWORD *)a1 + 13) + 64LL) + 80LL);
  if ( !v6 )
    return 0;
  v8 = ACAttachProcess(v6);
  v9 = CQEntry::Buffer(a1);
  if ( !v9 )
  {
    ACDetachProcess(v8);
    return 0;
  }
  CQEntry::AddRefBuffer(a1);
  v10 = *((unsigned int *)v9 + 11);
  v11 = *((_QWORD *)a1 + 13);
  v12 = *((_DWORD *)v9 + 11);
  v15 = 0;
  if ( (int)CPacket::Create(&v15, v11, v12, a2, a3) >= 0 )
  {
    v13 = CQEntry::Buffer(v15);
    v14 = (_QWORD *)(((unsigned __int64)v13 + 4) & -(__int64)(v13 != 0));
    memmove(v14, (char *)v9 + 4, v10 + 32);
    *v14 = 0;
  }
  ACDetachProcess(v8);
  CQEntry::ReleaseBuffer(a1);
  return v15;
}

```

## disassembly

```asm
0x140014980  push    rbx
0x140014982  push    rbp
0x140014983  push    rsi
0x140014984  push    rdi
0x140014985  push    r14
0x140014987  push    r15
0x140014989  sub     rsp, 38h
0x14001498d  mov     rax, [rcx+68h]
0x140014991  mov     rdi, rcx
0x140014994  mov     ebx, r8d
0x140014997  mov     r15d, edx
0x14001499a  mov     r9, [rax+40h]
0x14001499e  mov     rcx, [r9+50h]; Process
0x1400149a2  test    rcx, rcx
0x1400149a5  jnz     short loc_1400149AE
0x1400149a7  xor     eax, eax
0x1400149a9  jmp     loc_140014A44
0x1400149ae  call    ?ACAttachProcess@@YAPEAU_EPROCESS@@PEAU1@@Z; ACAttachProcess(_EPROCESS *)
0x1400149b3  mov     rcx, rdi; this
0x1400149b6  mov     rsi, rax
0x1400149b9  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x1400149be  mov     rbp, rax
0x1400149c1  test    rax, rax
0x1400149c4  jnz     short loc_1400149D0
0x1400149c6  mov     rcx, rsi; Process
0x1400149c9  call    ?ACDetachProcess@@YAXPEAU_EPROCESS@@@Z; ACDetachProcess(_EPROCESS *)
0x1400149ce  jmp     short loc_1400149A7
0x1400149d0  mov     rcx, rdi; this
0x1400149d3  call    ?AddRefBuffer@CQEntry@@QEBAXXZ; CQEntry::AddRefBuffer(void)
0x1400149d8  mov     r14d, [rbp+2Ch]
0x1400149dc  lea     rcx, [rsp+68h+arg_0]
0x1400149e1  mov     rdx, [rdi+68h]
0x1400149e5  mov     r8d, r14d
0x1400149e8  mov     r9d, r15d
0x1400149eb  mov     [rsp+68h+arg_0], 0
0x1400149f4  mov     [rsp+68h+var_48], ebx
0x1400149f8  call    ?Create@CPacket@@SAJPEAPEAV1@PEAU_DEVICE_OBJECT@@KW4ACPoolType@@H@Z; CPacket::Create(CPacket * *,_DEVICE_OBJECT *,ulong,ACPoolType,int)
0x1400149fd  test    eax, eax
0x1400149ff  js      short loc_140014A2F
0x140014a01  mov     rcx, [rsp+68h+arg_0]; this
0x140014a06  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x140014a0b  lea     r8, [r14+20h]; Size
0x140014a0f  lea     rdx, [rbp+4]; Src
0x140014a13  lea     rcx, [rax+4]
0x140014a17  neg     rax
0x140014a1a  sbb     rbx, rbx
0x140014a1d  and     rbx, rcx
0x140014a20  mov     rcx, rbx; void *
0x140014a23  call    memmove
0x140014a28  mov     qword ptr [rbx], 0
0x140014a2f  mov     rcx, rsi; Process
0x140014a32  call    ?ACDetachProcess@@YAXPEAU_EPROCESS@@@Z; ACDetachProcess(_EPROCESS *)
0x140014a37  mov     rcx, rdi; this
0x140014a3a  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x140014a3f  mov     rax, [rsp+68h+arg_0]
0x140014a44  add     rsp, 38h
0x140014a48  pop     r15
0x140014a4a  pop     r14
0x140014a4c  pop     rdi
0x140014a4d  pop     rsi
0x140014a4e  pop     rbp
0x140014a4f  pop     rbx
0x140014a50  retn
```
