# CMSMQMessage::GetStreamOfBody(ulong,void *,IStream * *)

- ea: `0x180015818`
- end: `0x1800158d3`
- name: `?GetStreamOfBody@CMSMQMessage@@IEAAJKPEAXPEAPEAUIStream@@@Z`
- size: `187`
- prototype: `int(CMSMQMessage *__hidden this, unsigned int, void *, struct IStream **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800158dc`

## callees

- `0x180015818`
- `0x180029010`

## import_xrefs

- `KERNEL32!GlobalHandle` at `0x180015843`
- `KERNEL32!GlobalHandle` at `0x180015843`
- `ole32!CreateStreamOnHGlobal` at `0x180015853`
- `ole32!CreateStreamOnHGlobal` at `0x180015853`

## pseudocode

```c
HRESULT __fastcall CMSMQMessage::GetStreamOfBody(CMSMQMessage *this, unsigned int a2, void *a3, struct IStream **a4)
{
  HGLOBAL v6; // rax
  HRESULT result; // eax
  int v8; // ebx
  LPSTREAM ppstm; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h]

  ppstm = 0;
  *a4 = 0;
  v6 = GlobalHandle(a3);
  result = CreateStreamOnHGlobal(v6, 0, &ppstm);
  if ( result >= 0 )
  {
    v10 = 0;
    v8 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
    if ( v8 < 0 || (v8 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD))ppstm->lpVtbl->SetSize)(ppstm, a2), v8 < 0) )
    {
      if ( ppstm )
        ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    }
    else
    {
      *a4 = ppstm;
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180015818  mov     rax, rsp
0x18001581b  mov     [rax+10h], rbx
0x18001581f  mov     [rax+18h], rsi
0x180015823  mov     [rax+8], rcx
0x180015827  push    rdi
0x180015828  sub     rsp, 30h
0x18001582c  mov     rcx, r8; pMem
0x18001582f  mov     esi, edx
0x180015831  mov     rdi, r9
0x180015834  mov     qword ptr [rax+8], 0
0x18001583c  mov     qword ptr [r9], 0
0x180015843  call    cs:__imp_GlobalHandle
0x180015849  lea     r8, [rsp+38h+ppstm]; ppstm
0x18001584e  xor     edx, edx; fDeleteOnRelease
0x180015850  mov     rcx, rax; hGlobal
0x180015853  call    cs:__imp_CreateStreamOnHGlobal
0x180015859  test    eax, eax
0x18001585b  js      short loc_1800158C3
0x18001585d  mov     rcx, [rsp+38h+ppstm]
0x180015862  xor     r9d, r9d
0x180015865  mov     [rsp+38h+arg_18], 0
0x18001586e  xor     r8d, r8d
0x180015871  mov     rdx, [rsp+38h+arg_18]
0x180015876  mov     rax, [rcx]
0x180015879  mov     rax, [rax+28h]
0x18001587d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015882  mov     ebx, eax
0x180015884  test    eax, eax
0x180015886  js      short loc_1800158AB
0x180015888  mov     rcx, [rsp+38h+ppstm]
0x18001588d  mov     edx, esi
0x18001588f  mov     rax, [rcx]
0x180015892  mov     rax, [rax+30h]
0x180015896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001589b  mov     ebx, eax
0x18001589d  test    eax, eax
0x18001589f  js      short loc_1800158AB
0x1800158a1  mov     rax, [rsp+38h+ppstm]
0x1800158a6  mov     [rdi], rax
0x1800158a9  jmp     short loc_1800158C1
0x1800158ab  mov     rcx, [rsp+38h+ppstm]
0x1800158b0  test    rcx, rcx
0x1800158b3  jz      short loc_1800158C1
0x1800158b5  mov     rax, [rcx]
0x1800158b8  mov     rax, [rax+10h]
0x1800158bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158c1  mov     eax, ebx
0x1800158c3  mov     rbx, [rsp+38h+arg_8]
0x1800158c8  mov     rsi, [rsp+38h+arg_10]
0x1800158cd  add     rsp, 30h
0x1800158d1  pop     rdi
0x1800158d2  retn
```
