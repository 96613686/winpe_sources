# std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>>>(std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>> &,std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *> *)

- ea: `0x18001c464`
- end: `0x18001c493`
- name: `??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `47`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cb38`
- `0x18001cc00`
- `0x18001f2e4`
- `0x180020b28`

## callees

- `0x18001c464`
- `0x18001c4d4`

## pseudocode

```c
_QWORD *__fastcall std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>>>(
        __int64 a1,
        __int64 a2)
{
  _QWORD *result; // rax
  _QWORD *v3; // rdx
  _QWORD *v4; // rbx

  result = *(_QWORD **)(a2 + 8);
  *result = 0;
  v3 = *(_QWORD **)a2;
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      result = (_QWORD *)std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>>>();
      v3 = v4;
    }
    while ( v4 );
  }
  return result;
}

```

## disassembly

```asm
0x18001c464  push    rbx
0x18001c466  sub     rsp, 20h
0x18001c46a  mov     rax, [rdx+8]
0x18001c46e  mov     qword ptr [rax], 0
0x18001c475  mov     rdx, [rdx]
0x18001c478  test    rdx, rdx
0x18001c47b  jz      short loc_18001C48D
0x18001c47d  mov     rbx, [rdx]
0x18001c480  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>>>(std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *>> &,std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *> *)
0x18001c485  mov     rdx, rbx
0x18001c488  test    rbx, rbx
0x18001c48b  jnz     short loc_18001C47D
0x18001c48d  add     rsp, 20h
0x18001c491  pop     rbx
0x18001c492  retn
```
