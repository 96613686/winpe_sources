# CLoader::GC_UpdateForReleasedObject(CObject *)

- ea: `0x180008918`
- end: `0x1800089de`
- name: `?GC_UpdateForReleasedObject@CLoader@@QEAAXPEAVCObject@@@Z`
- size: `198`
- prototype: `void __fastcall(CLoader *__hidden this, struct CObject *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180009550`
- `0x18000a1e4`

## callees

- `0x180008840`
- `0x180008918`
- `0x180010010`

## pseudocode

```c
void __fastcall CLoader::GC_UpdateForReleasedObject(CLoader *this, struct CObject *a2)
{
  __int64 *v4; // rcx
  unsigned int v5; // r8d
  __int64 v6; // rdx
  __int64 v7; // rax
  char v8; // r11

  if ( a2 )
  {
    *(_QWORD *)a2 = *((_QWORD *)this + 79);
    *((_QWORD *)this + 79) = a2;
  }
  v4 = *(__int64 **)(*((_QWORD *)this + 77) + 200LL);
  v5 = *((_DWORD *)v4 + 2);
  if ( v5 )
  {
    v6 = *v4;
    v7 = 0;
    while ( *(struct CObject **)(v6 + 8 * v7) != a2 )
    {
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= v5 )
        goto LABEL_9;
    }
    *(_QWORD *)(v6 + 8 * v7) = 0;
  }
LABEL_9:
  if ( *(_QWORD *)((char *)a2 + 36) != *(_QWORD *)&CLSID_DirectMusicScript.Data1
    || *(_QWORD *)((char *)a2 + 44) != *(_QWORD *)CLSID_DirectMusicScript.Data4 )
  {
    CLoader::GC_TraverseHelper(this, a2, a2, 1);
    CLoader::GC_TraverseHelper(this, a2, a2, 0);
    if ( !v8 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 23) + 16LL))(*((_QWORD *)a2 + 23));
      *((_QWORD *)a2 + 23) = 0;
    }
  }
}

```

## disassembly

```asm
0x180008918  mov     [rsp+arg_0], rbx
0x18000891d  push    rdi
0x18000891e  sub     rsp, 20h
0x180008922  mov     rbx, rdx
0x180008925  mov     rdi, rcx
0x180008928  test    rdx, rdx
0x18000892b  jz      short loc_18000893E
0x18000892d  mov     rax, [rcx+278h]
0x180008934  mov     [rdx], rax
0x180008937  mov     [rcx+278h], rdx
0x18000893e  mov     rax, [rcx+268h]
0x180008945  mov     rcx, [rax+0C8h]
0x18000894c  mov     r8d, [rcx+8]
0x180008950  test    r8d, r8d
0x180008953  jz      short loc_180008971
0x180008955  mov     rdx, [rcx]
0x180008958  xor     eax, eax
0x18000895a  cmp     [rdx+rax*8], rbx
0x18000895e  jz      short loc_180008969
0x180008960  inc     eax
0x180008962  cmp     eax, r8d
0x180008965  jb      short loc_18000895A
0x180008967  jmp     short loc_180008971
0x180008969  mov     qword ptr [rdx+rax*8], 0
0x180008971  mov     rax, [rbx+24h]
0x180008975  cmp     rax, qword ptr cs:CLSID_DirectMusicScript.Data1
0x18000897c  jnz     short loc_18000898B
0x18000897e  mov     rax, [rbx+2Ch]
0x180008982  cmp     rax, qword ptr cs:CLSID_DirectMusicScript.Data4
0x180008989  jz      short loc_1800089D3
0x18000898b  mov     r9b, 1; bool
0x18000898e  mov     r8, rbx; struct CObject *
0x180008991  mov     rdx, rbx; struct CObject *
0x180008994  mov     rcx, rdi; this
0x180008997  call    ?GC_TraverseHelper@CLoader@@AEAA_NPEAVCObject@@0_N@Z; CLoader::GC_TraverseHelper(CObject *,CObject *,bool)
0x18000899c  xor     r9d, r9d; bool
0x18000899f  mov     r8, rbx; struct CObject *
0x1800089a2  mov     rdx, rbx; struct CObject *
0x1800089a5  mov     rcx, rdi; this
0x1800089a8  mov     r11b, al
0x1800089ab  call    ?GC_TraverseHelper@CLoader@@AEAA_NPEAVCObject@@0_N@Z; CLoader::GC_TraverseHelper(CObject *,CObject *,bool)
0x1800089b0  test    r11b, r11b
0x1800089b3  jnz     short loc_1800089D3
0x1800089b5  mov     rcx, [rbx+0B8h]
0x1800089bc  mov     rax, [rcx]
0x1800089bf  mov     rax, [rax+10h]
0x1800089c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c8  mov     qword ptr [rbx+0B8h], 0
0x1800089d3  mov     rbx, [rsp+28h+arg_0]
0x1800089d8  add     rsp, 20h
0x1800089dc  pop     rdi
0x1800089dd  retn
```
