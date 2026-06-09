# CRenderer::UpdatePalette(COleObject *)

- ea: `0x180076438`
- end: `0x1800765d3`
- name: `?UpdatePalette@CRenderer@@AEAAXPEAVCOleObject@@@Z`
- size: `411`
- prototype: `void __fastcall(CRenderer *__hidden this, struct COleObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180024328`

## callees

- `0x1800427ac`
- `0x180076438`
- `0x18008fe00`
- `0x1800931b0`
- `0x180093bb2`
- `0x180095010`

## string_xrefs

- `0x1800764f8`: `CoTaskMemAlloc`

## pseudocode

```c
void __fastcall CRenderer::UpdatePalette(CRenderer *this, struct COleObject *a2)
{
  unsigned int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // [rsp+70h] [rbp+18h] BYREF

  v2 = (unsigned int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a2 + 9);
  v3 = 0;
  if ( !(**v2)(v2, &IID_IViewObject, &v3) )
  {
    (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, 1, 0xFFFFFFFFLL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x180076438  mov     r11, rsp
0x18007643b  mov     [r11+8], rbx
0x18007643f  push    rbp
0x180076440  push    rsi
0x180076441  push    rdi
0x180076442  sub     rsp, 40h
0x180076446  mov     rdi, rcx
0x180076449  mov     qword ptr [r11+10h], 0
0x180076451  mov     rcx, [rdx+48h]
0x180076455  lea     r8, [r11+18h]
0x180076459  mov     qword ptr [r11+18h], 0
0x180076461  lea     rdx, IID_IViewObject
0x180076468  mov     rax, [rcx]
0x18007646b  mov     rax, [rax]
0x18007646e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076473  test    eax, eax
0x180076475  jnz     loc_1800765C5
0x18007647b  mov     rcx, [rsp+58h+arg_10]
0x180076480  lea     rdx, [rsp+58h+arg_8]
0x180076485  mov     [rsp+58h+var_28], rdx
0x18007648a  xor     r9d, r9d
0x18007648d  mov     [rsp+58h+var_30], 0
0x180076496  or      r8d, 0FFFFFFFFh
0x18007649a  mov     [rsp+58h+var_38], 0
0x1800764a3  mov     rax, [rcx]
0x1800764a6  lea     edx, [r9+1]
0x1800764aa  mov     rax, [rax+20h]
0x1800764ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800764b3  test    eax, eax
0x1800764b5  jnz     loc_1800765B4
0x1800764bb  mov     rax, [rsp+58h+arg_8]
0x1800764c0  test    rax, rax
0x1800764c3  jz      loc_1800765B4
0x1800764c9  mov     rcx, [rdi+128h]
0x1800764d0  test    rcx, rcx
0x1800764d3  jnz     short loc_1800764E1
0x1800764d5  mov     [rdi+128h], rax
0x1800764dc  jmp     loc_1800765B4
0x1800764e1  movzx   esi, word ptr [rcx+2]
0x1800764e5  movzx   ebp, word ptr [rax+2]
0x1800764e9  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x1800764ee  lea     rbx, [rax+60h]
0x1800764f2  cmp     qword ptr [rbx], 0
0x1800764f6  jnz     short loc_18007650C
0x1800764f8  lea     r8, aCotaskmemalloc; "CoTaskMemAlloc"
0x1800764ff  mov     edx, 1
0x180076504  mov     rcx, rbx
0x180076507  call    SetProcAddr
0x18007650c  mov     rax, [rbx]
0x18007650f  test    rax, rax
0x180076512  jz      loc_1800765AA
0x180076518  add     ebp, esi
0x18007651a  lea     ecx, ds:4[rbp*4]
0x180076521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076526  mov     rbx, rax
0x180076529  test    rax, rax
0x18007652c  jz      short loc_1800765AA
0x18007652e  mov     rdx, [rdi+128h]
0x180076535  lea     rcx, [rax+4]; void *
0x180076539  movzx   r8d, word ptr [rdx+2]
0x18007653e  add     rdx, 4; Src
0x180076542  shl     r8, 2; Size
0x180076546  call    memcpy_0
0x18007654b  mov     rdx, [rsp+58h+arg_8]
0x180076550  mov     rax, [rdi+128h]
0x180076557  movzx   r8d, word ptr [rdx+2]
0x18007655c  add     rdx, 4; Src
0x180076560  movzx   ecx, word ptr [rax+2]
0x180076564  inc     rcx
0x180076567  shl     r8, 2; Size
0x18007656b  lea     rcx, [rbx+rcx*4]; void *
0x18007656f  call    memcpy_0
0x180076574  mov     rax, [rsp+58h+arg_8]
0x180076579  movzx   ecx, word ptr [rax]
0x18007657c  mov     [rbx], cx
0x18007657f  mov     rcx, [rdi+128h]
0x180076586  mov     rax, [rsp+58h+arg_8]
0x18007658b  movzx   ecx, word ptr [rcx+2]
0x18007658f  add     cx, [rax+2]
0x180076593  mov     [rbx+2], cx
0x180076597  mov     rcx, [rdi+128h]; void *
0x18007659e  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x1800765a3  mov     [rdi+128h], rbx
0x1800765aa  mov     rcx, [rsp+58h+arg_8]; void *
0x1800765af  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x1800765b4  mov     rcx, [rsp+58h+arg_10]
0x1800765b9  mov     rax, [rcx]
0x1800765bc  mov     rax, [rax+10h]
0x1800765c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765c5  mov     rbx, [rsp+58h+arg_0]
0x1800765ca  add     rsp, 40h
0x1800765ce  pop     rdi
0x1800765cf  pop     rsi
0x1800765d0  pop     rbp
0x1800765d1  retn
```
