# ATL::CDynamicAccessor::FreeRecordMemory(IRowset *)

- ea: `0x180008db4`
- end: `0x180008ee9`
- name: `?FreeRecordMemory@CDynamicAccessor@ATL@@QEAAXPEAUIRowset@@@Z`
- size: `309`
- prototype: `void __fastcall(ATL::CDynamicAccessor *this, struct IRowset *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b98`
- `0x1800094a8`
- `0x1800099e4`
- `0x18000a330`

## callees

- `0x180008db4`
- `0x180008ef0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e29`

## pseudocode

```c
void __fastcall ATL::CDynamicAccessor::FreeRecordMemory(ATL::CDynamicAccessor *this, struct IRowset *a2)
{
  __int64 v2; // rsi
  __int64 *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  LPVOID *v13; // rbx
  unsigned __int64 v14; // rax
  __int64 v15; // r8
  unsigned __int16 v16; // r10
  unsigned __int8 *v17; // rdx
  __int64 v18; // r9
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rax

  v2 = 0;
  if ( *((_QWORD *)this + 3) )
  {
    v5 = (__int64 *)((char *)this + 40);
    while ( 1 )
    {
      v6 = *((_QWORD *)this + 4);
      if ( v6 )
      {
        if ( *(_BYTE *)(v6 + v2) == 1 )
        {
          v7 = *((_QWORD *)this + 5);
          v8 = *(_QWORD *)(v7 + 80 * v2 + 8);
          v9 = v8 + *(_QWORD *)(v7 + 80 * v2 + 32);
          if ( v9 + 7 < v9 )
          {
            v10 = 10;
            goto LABEL_7;
          }
          v14 = ((v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
          v10 = ((v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 11;
          if ( v14 + 3 >= v14 )
LABEL_7:
            v11 = v10 & 0xFFFFFFFFFFFFFFFCuLL;
          else
            v11 = -1;
          v12 = *((_QWORD *)this + 2);
          if ( *(_DWORD *)(v12 + v11) != 3 )
          {
            v13 = (LPVOID *)(v8 + v12);
            if ( v8 + v12 )
            {
              if ( *v13 )
              {
                CoTaskMemFree(*v13);
                *v13 = 0;
              }
            }
          }
          v5 = (__int64 *)((char *)this + 40);
          goto LABEL_24;
        }
        v5 = (__int64 *)((char *)this + 40);
      }
      v15 = *v5;
      v16 = *(_WORD *)(*v5 + 80 * v2 + 40);
      if ( ((v16 - 9) & 0xFFFB) != 0 )
      {
        v17 = (unsigned __int8 *)(*((_QWORD *)this + 2) + *(_QWORD *)(v15 + 80 * v2 + 8));
LABEL_23:
        ATL::CAccessorBase::FreeType(v16, v17, a2);
        goto LABEL_24;
      }
      v18 = *(_QWORD *)(v15 + 80 * v2 + 8);
      v19 = v18 + *(_QWORD *)(v15 + 80 * v2 + 32);
      if ( v19 + 7 < v19 )
        break;
      v23 = ((v19 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
      v20 = ((v19 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 11;
      if ( v23 + 3 >= v23 )
        goto LABEL_20;
      v21 = -1;
LABEL_21:
      v22 = *((_QWORD *)this + 2);
      if ( !*(_DWORD *)(v22 + v21) )
      {
        v17 = (unsigned __int8 *)(v18 + v22);
        goto LABEL_23;
      }
LABEL_24:
      v2 = (unsigned int)(v2 + 1);
      if ( (unsigned __int64)(unsigned int)v2 >= *((_QWORD *)this + 3) )
        return;
    }
    v20 = 10;
LABEL_20:
    v21 = v20 & 0xFFFFFFFFFFFFFFFCuLL;
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x180008db4  push    rbx
0x180008db6  push    rbp
0x180008db7  push    rsi
0x180008db8  push    rdi
0x180008db9  push    r14
0x180008dbb  sub     rsp, 20h
0x180008dbf  xor     esi, esi
0x180008dc1  mov     r14, rdx
0x180008dc4  mov     rdi, rcx
0x180008dc7  cmp     [rcx+18h], rsi
0x180008dcb  jbe     loc_180008EC7
0x180008dd1  lea     rbx, [rcx+28h]
0x180008dd5  mov     rcx, [rdi+20h]
0x180008dd9  test    rcx, rcx
0x180008ddc  jz      short loc_180008E57
0x180008dde  cmp     byte ptr [rcx+rsi], 1
0x180008de2  jnz     short loc_180008E53
0x180008de4  mov     rax, [rdi+28h]
0x180008de8  lea     rcx, [rsi+rsi*4]
0x180008dec  add     rcx, rcx
0x180008def  mov     rdx, [rax+rcx*8+8]
0x180008df4  mov     rcx, [rax+rcx*8+20h]
0x180008df9  add     rcx, rdx
0x180008dfc  lea     rax, [rcx+7]
0x180008e00  cmp     rax, rcx
0x180008e03  jnb     short loc_180008E3C
0x180008e05  mov     ecx, 0Ah
0x180008e0a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008e0e  mov     rax, [rdi+10h]
0x180008e12  cmp     dword ptr [rax+rcx], 3
0x180008e16  jz      short loc_180008E36
0x180008e18  lea     rbx, [rdx+rax]
0x180008e1c  test    rbx, rbx
0x180008e1f  jz      short loc_180008E36
0x180008e21  mov     rcx, [rbx]; pv
0x180008e24  test    rcx, rcx
0x180008e27  jz      short loc_180008E36
0x180008e29  call    cs:__imp_CoTaskMemFree
0x180008e2f  mov     qword ptr [rbx], 0
0x180008e36  lea     rbx, [rdi+28h]
0x180008e3a  jmp     short loc_180008EB9
0x180008e3c  and     rax, 0FFFFFFFFFFFFFFF8h
0x180008e40  add     rax, 8
0x180008e44  lea     rcx, [rax+3]
0x180008e48  cmp     rcx, rax
0x180008e4b  jnb     short loc_180008E0A
0x180008e4d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008e51  jmp     short loc_180008E0E
0x180008e53  lea     rbx, [rdi+28h]
0x180008e57  mov     r8, [rbx]
0x180008e5a  lea     rdx, [rsi+rsi*4]
0x180008e5e  add     rdx, rdx
0x180008e61  mov     ecx, 0FFFBh
0x180008e66  movzx   r10d, word ptr [r8+rdx*8+28h]
0x180008e6c  lea     eax, [r10-9]
0x180008e70  test    cx, ax
0x180008e73  jz      short loc_180008E80
0x180008e75  mov     rdx, [r8+rdx*8+8]
0x180008e7a  add     rdx, [rdi+10h]
0x180008e7e  jmp     short loc_180008EAD
0x180008e80  mov     r9, [r8+rdx*8+8]
0x180008e85  mov     rcx, [r8+rdx*8+20h]
0x180008e8a  add     rcx, r9
0x180008e8d  lea     rax, [rcx+7]
0x180008e91  cmp     rax, rcx
0x180008e94  jnb     short loc_180008ED2
0x180008e96  mov     ecx, 0Ah
0x180008e9b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008e9f  mov     rax, [rdi+10h]
0x180008ea3  cmp     dword ptr [rax+rcx], 0
0x180008ea7  jnz     short loc_180008EB9
0x180008ea9  lea     rdx, [r9+rax]; unsigned __int8 *
0x180008ead  mov     r8, r14; struct IRowset *
0x180008eb0  movzx   ecx, r10w; unsigned __int16
0x180008eb4  call    ?FreeType@CAccessorBase@ATL@@SAXGPEAEPEAUIRowset@@@Z; ATL::CAccessorBase::FreeType(ushort,uchar *,IRowset *)
0x180008eb9  inc     esi
0x180008ebb  mov     eax, esi
0x180008ebd  cmp     rax, [rdi+18h]
0x180008ec1  jb      loc_180008DD5
0x180008ec7  add     rsp, 20h
0x180008ecb  pop     r14
0x180008ecd  pop     rdi
0x180008ece  pop     rsi
0x180008ecf  pop     rbp
0x180008ed0  pop     rbx
0x180008ed1  retn
0x180008ed2  and     rax, 0FFFFFFFFFFFFFFF8h
0x180008ed6  add     rax, 8
0x180008eda  lea     rcx, [rax+3]
0x180008ede  cmp     rcx, rax
0x180008ee1  jnb     short loc_180008E9B
0x180008ee3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008ee7  jmp     short loc_180008E9F
```
