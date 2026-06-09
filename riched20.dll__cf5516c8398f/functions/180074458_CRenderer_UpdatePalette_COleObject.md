# CRenderer::UpdatePalette(COleObject *)

- ea: `0x180074458`
- end: `0x1800745f2`
- name: `?UpdatePalette@CRenderer@@AEAAXPEAVCOleObject@@@Z`
- size: `410`
- prototype: `void __fastcall(CRenderer *__hidden this, struct COleObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180020f08`

## callees

- `0x180041adc`
- `0x180074458`
- `0x18008d624`
- `0x1800907ac`
- `0x1800910f2`
- `0x180092010`

## string_xrefs

- `0x180074518`: `CoTaskMemAlloc`

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
0x180074458  mov     r11, rsp
0x18007445b  mov     [r11+8], rbx
0x18007445f  push    rbp
0x180074460  push    rsi
0x180074461  push    rdi
0x180074462  sub     rsp, 40h
0x180074466  mov     rdi, rcx
0x180074469  mov     qword ptr [r11+10h], 0
0x180074471  mov     rcx, [rdx+48h]
0x180074475  lea     r8, [r11+18h]
0x180074479  mov     qword ptr [r11+18h], 0
0x180074481  lea     rdx, IID_IViewObject
0x180074488  mov     rax, [rcx]
0x18007448b  mov     rax, [rax]
0x18007448e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074493  test    eax, eax
0x180074495  jnz     loc_1800745E5
0x18007449b  mov     rcx, [rsp+58h+arg_10]
0x1800744a0  lea     rdx, [rsp+58h+arg_8]
0x1800744a5  mov     [rsp+58h+var_28], rdx
0x1800744aa  xor     r9d, r9d
0x1800744ad  mov     [rsp+58h+var_30], 0
0x1800744b6  or      r8d, 0FFFFFFFFh
0x1800744ba  mov     [rsp+58h+var_38], 0
0x1800744c3  mov     rax, [rcx]
0x1800744c6  lea     edx, [r9+1]
0x1800744ca  mov     rax, [rax+20h]
0x1800744ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800744d3  test    eax, eax
0x1800744d5  jnz     loc_1800745D4
0x1800744db  mov     rax, [rsp+58h+arg_8]
0x1800744e0  test    rax, rax
0x1800744e3  jz      loc_1800745D4
0x1800744e9  mov     rcx, [rdi+128h]
0x1800744f0  test    rcx, rcx
0x1800744f3  jnz     short loc_180074501
0x1800744f5  mov     [rdi+128h], rax
0x1800744fc  jmp     loc_1800745D4
0x180074501  movzx   esi, word ptr [rcx+2]
0x180074505  movzx   ebp, word ptr [rax+2]
0x180074509  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007450e  lea     rbx, [rax+60h]
0x180074512  cmp     qword ptr [rbx], 0
0x180074516  jnz     short loc_18007452C
0x180074518  lea     r8, aCotaskmemalloc; "CoTaskMemAlloc"
0x18007451f  mov     edx, 1
0x180074524  mov     rcx, rbx
0x180074527  call    SetProcAddr
0x18007452c  mov     rax, [rbx]
0x18007452f  test    rax, rax
0x180074532  jz      loc_1800745CA
0x180074538  add     ebp, esi
0x18007453a  lea     ecx, ds:4[rbp*4]
0x180074541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074546  mov     rbx, rax
0x180074549  test    rax, rax
0x18007454c  jz      short loc_1800745CA
0x18007454e  mov     rdx, [rdi+128h]
0x180074555  lea     rcx, [rax+4]; void *
0x180074559  movzx   r8d, word ptr [rdx+2]
0x18007455e  add     rdx, 4; Src
0x180074562  shl     r8, 2; Size
0x180074566  call    memcpy_0
0x18007456b  mov     rdx, [rsp+58h+arg_8]
0x180074570  mov     rax, [rdi+128h]
0x180074577  movzx   r8d, word ptr [rdx+2]
0x18007457c  add     rdx, 4; Src
0x180074580  movzx   ecx, word ptr [rax+2]
0x180074584  inc     rcx
0x180074587  shl     r8, 2; Size
0x18007458b  lea     rcx, [rbx+rcx*4]; void *
0x18007458f  call    memcpy_0
0x180074594  mov     rax, [rsp+58h+arg_8]
0x180074599  movzx   ecx, word ptr [rax]
0x18007459c  mov     [rbx], cx
0x18007459f  mov     rcx, [rdi+128h]
0x1800745a6  mov     rax, [rsp+58h+arg_8]
0x1800745ab  movzx   ecx, word ptr [rcx+2]
0x1800745af  add     cx, [rax+2]
0x1800745b3  mov     [rbx+2], cx
0x1800745b7  mov     rcx, [rdi+128h]; void *
0x1800745be  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x1800745c3  mov     [rdi+128h], rbx
0x1800745ca  mov     rcx, [rsp+58h+arg_8]; void *
0x1800745cf  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x1800745d4  mov     rcx, [rsp+58h+arg_10]
0x1800745d9  mov     rax, [rcx]
0x1800745dc  mov     rax, [rax+10h]
0x1800745e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745e5  mov     rbx, [rsp+58h+arg_0]
0x1800745ea  add     rsp, 40h
0x1800745ee  pop     rdi
0x1800745ef  pop     rsi
0x1800745f0  pop     rbp
0x1800745f1  retn
```
