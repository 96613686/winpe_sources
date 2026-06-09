# CNFFMappedStream::Close(long *)

- ea: `0x1800401b0`
- end: `0x18004023a`
- name: `?Close@CNFFMappedStream@@UEAAXPEAJ@Z`
- size: `138`
- prototype: `void __fastcall(CNFFMappedStream *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800401b0`
- `0x180040240`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800401ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800401ee`

## pseudocode

```c
void __fastcall CNFFMappedStream::Close(CNFFMappedStream *this, int *a2)
{
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 24LL))(
    *(_QWORD *)(*((_QWORD *)this + 1) + 104LL),
    0xFFFFFFFFLL);
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) != -1 )
  {
    CNFFMappedStream::WriteMappedStream(this);
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 4) &= 0xFFFFFFE5;
    *((_QWORD *)this + 4) = 0;
    *((_DWORD *)this + 12) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 104LL));
  *a2 = 0;
}

```

## disassembly

```asm
0x1800401b0  mov     [rsp+arg_0], rbx
0x1800401b5  push    rdi
0x1800401b6  sub     rsp, 20h
0x1800401ba  mov     rax, [rcx+8]
0x1800401be  mov     rbx, rcx
0x1800401c1  mov     rdi, rdx
0x1800401c4  or      edx, 0FFFFFFFFh
0x1800401c7  mov     rcx, [rax+68h]
0x1800401cb  mov     rax, [rcx]
0x1800401ce  mov     rax, [rax+18h]
0x1800401d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401d7  mov     rax, [rbx+8]
0x1800401db  cmp     qword ptr [rax+60h], 0FFFFFFFFFFFFFFFFh
0x1800401e0  jz      short loc_180040215
0x1800401e2  mov     rcx, rbx; this
0x1800401e5  call    ?WriteMappedStream@CNFFMappedStream@@AEAAJXZ; CNFFMappedStream::WriteMappedStream(void)
0x1800401ea  mov     rcx, [rbx+18h]; pv
0x1800401ee  call    cs:__imp_CoTaskMemFree
0x1800401f4  mov     qword ptr [rbx+18h], 0
0x1800401fc  and     dword ptr [rbx+10h], 0FFFFFFE5h
0x180040200  xor     eax, eax
0x180040202  mov     qword ptr [rbx+20h], 0
0x18004020a  mov     [rbx+30h], eax
0x18004020d  mov     qword ptr [rbx+28h], 0
0x180040215  mov     rax, [rbx+8]
0x180040219  mov     rcx, [rax+68h]
0x18004021d  mov     rax, [rcx]
0x180040220  mov     rax, [rax+20h]
0x180040224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040229  mov     rbx, [rsp+28h+arg_0]
0x18004022e  mov     dword ptr [rdi], 0
0x180040234  add     rsp, 20h
0x180040238  pop     rdi
0x180040239  retn
```
