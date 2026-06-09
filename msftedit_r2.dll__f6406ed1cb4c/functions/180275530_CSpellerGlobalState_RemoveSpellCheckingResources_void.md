# CSpellerGlobalState::RemoveSpellCheckingResources(void)

- ea: `0x180275530`
- end: `0x180275666`
- name: `?RemoveSpellCheckingResources@CSpellerGlobalState@@AEAAXXZ`
- size: `310`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180273b34`
- `0x180276fd0`

## callees

- `0x18006ad18`
- `0x18013dac8`
- `0x180273dd8`
- `0x180275530`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18027557e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802755d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18027563b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18027557e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802755d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18027563b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180275614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180275614`

## pseudocode

```c
void __fastcall CSpellerGlobalState::RemoveSpellCheckingResources(CSpellerGlobalState *this, unsigned int a2)
{
  __int64 v2; // rbx
  int v4; // edi
  void *v5; // rcx
  __int64 v6; // rbx
  int v7; // edi
  CSpellCheckSpeller *v8; // rcx
  __int64 v9; // rbx
  int v10; // edi
  HSTRING *v11; // rbx

  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    if ( *(_DWORD *)(v2 + 4) )
    {
      v4 = 0;
      do
      {
        if ( v4 < 0 || (unsigned int)v4 >= *(_DWORD *)(v2 + 4) )
          v5 = 0;
        else
          v5 = *(void **)((unsigned int)(*(_DWORD *)(v2 + 8) * v4) + *(_QWORD *)(v2 + 16));
        operator delete(v5);
        v2 = *((_QWORD *)this + 5);
        ++v4;
      }
      while ( (unsigned int)v4 < *(_DWORD *)(v2 + 4) );
    }
    free(*(void **)(v2 + 16));
    *(_QWORD *)(v2 + 16) = 0;
    *(_QWORD *)v2 = 0;
  }
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 4) )
    {
      v7 = 0;
      do
      {
        if ( v7 >= 0 && (unsigned int)v7 < *(_DWORD *)(v6 + 4) )
        {
          v8 = *(CSpellCheckSpeller **)((unsigned int)(*(_DWORD *)(v6 + 8) * v7) + *(_QWORD *)(v6 + 16));
          if ( v8 )
            CSpellCheckSpeller::`scalar deleting destructor'(v8, a2);
        }
        v6 = *((_QWORD *)this + 3);
        ++v7;
      }
      while ( (unsigned int)v7 < *(_DWORD *)(v6 + 4) );
    }
    free(*(void **)(v6 + 16));
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)v6 = 0;
  }
  v9 = *((_QWORD *)this + 4);
  if ( v9 )
  {
    if ( *(_DWORD *)(v9 + 4) )
    {
      v10 = 0;
      do
      {
        if ( v10 >= 0 && (unsigned int)v10 < *(_DWORD *)(v9 + 4) )
        {
          v11 = *(HSTRING **)((unsigned int)(*(_DWORD *)(v9 + 8) * v10) + *(_QWORD *)(v9 + 16));
          if ( v11 )
          {
            WindowsDeleteString(v11[1]);
            v11[1] = 0;
            operator delete(v11);
          }
        }
        v9 = *((_QWORD *)this + 4);
        ++v10;
      }
      while ( (unsigned int)v10 < *(_DWORD *)(v9 + 4) );
    }
    free(*(void **)(v9 + 16));
    *(_QWORD *)(v9 + 16) = 0;
    *(_QWORD *)v9 = 0;
  }
  if ( *((_QWORD *)this + 6) )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
}

```

## disassembly

```asm
0x180275530  push    rbx
0x180275532  push    rbp
0x180275533  push    rsi
0x180275534  push    rdi
0x180275535  sub     rsp, 28h
0x180275539  mov     rbx, [rcx+28h]
0x18027553d  xor     ebp, ebp
0x18027553f  mov     rsi, rcx
0x180275542  test    rbx, rbx
0x180275545  jz      short loc_180275591
0x180275547  cmp     [rbx+4], ebp
0x18027554a  jbe     short loc_18027557A
0x18027554c  mov     edi, ebp
0x18027554e  test    edi, edi
0x180275550  js      short loc_180275567
0x180275552  cmp     edi, [rbx+4]
0x180275555  jnb     short loc_180275567
0x180275557  mov     rax, [rbx+10h]
0x18027555b  mov     ecx, edi
0x18027555d  imul    ecx, [rbx+8]
0x180275561  mov     rcx, [rcx+rax]
0x180275565  jmp     short loc_18027556A
0x180275567  mov     rcx, rbp; Block
0x18027556a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18027556f  mov     rbx, [rsi+28h]
0x180275573  inc     edi
0x180275575  cmp     edi, [rbx+4]
0x180275578  jb      short loc_18027554E
0x18027557a  mov     rcx, [rbx+10h]; Block
0x18027557e  call    cs:__imp_free
0x180275585  nop     dword ptr [rax+rax+00h]
0x18027558a  mov     [rbx+10h], rbp
0x18027558e  mov     [rbx], rbp
0x180275591  mov     rbx, [rsi+18h]
0x180275595  test    rbx, rbx
0x180275598  jz      short loc_1802755E4
0x18027559a  cmp     [rbx+4], ebp
0x18027559d  jbe     short loc_1802755CD
0x18027559f  mov     edi, ebp
0x1802755a1  test    edi, edi
0x1802755a3  js      short loc_1802755C2
0x1802755a5  cmp     edi, [rbx+4]
0x1802755a8  jnb     short loc_1802755C2
0x1802755aa  mov     rax, [rbx+10h]
0x1802755ae  mov     ecx, edi
0x1802755b0  imul    ecx, [rbx+8]
0x1802755b4  mov     rcx, [rcx+rax]; this
0x1802755b8  test    rcx, rcx
0x1802755bb  jz      short loc_1802755C2
0x1802755bd  call    ??_GCSpellCheckSpeller@@QEAAPEAXI@Z; CSpellCheckSpeller::`scalar deleting destructor'(uint)
0x1802755c2  mov     rbx, [rsi+18h]
0x1802755c6  inc     edi
0x1802755c8  cmp     edi, [rbx+4]
0x1802755cb  jb      short loc_1802755A1
0x1802755cd  mov     rcx, [rbx+10h]; Block
0x1802755d1  call    cs:__imp_free
0x1802755d8  nop     dword ptr [rax+rax+00h]
0x1802755dd  mov     [rbx+10h], rbp
0x1802755e1  mov     [rbx], rbp
0x1802755e4  mov     rbx, [rsi+20h]
0x1802755e8  test    rbx, rbx
0x1802755eb  jz      short loc_18027564E
0x1802755ed  cmp     [rbx+4], ebp
0x1802755f0  jbe     short loc_180275637
0x1802755f2  mov     edi, ebp
0x1802755f4  test    edi, edi
0x1802755f6  js      short loc_18027562C
0x1802755f8  cmp     edi, [rbx+4]
0x1802755fb  jnb     short loc_18027562C
0x1802755fd  mov     rax, [rbx+10h]
0x180275601  mov     ecx, edi
0x180275603  imul    ecx, [rbx+8]
0x180275607  mov     rbx, [rcx+rax]
0x18027560b  test    rbx, rbx
0x18027560e  jz      short loc_18027562C
0x180275610  mov     rcx, [rbx+8]; string
0x180275614  call    cs:__imp_WindowsDeleteString
0x18027561b  nop     dword ptr [rax+rax+00h]
0x180275620  mov     rcx, rbx; Block
0x180275623  mov     [rbx+8], rbp
0x180275627  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18027562c  mov     rbx, [rsi+20h]
0x180275630  inc     edi
0x180275632  cmp     edi, [rbx+4]
0x180275635  jb      short loc_1802755F4
0x180275637  mov     rcx, [rbx+10h]; Block
0x18027563b  call    cs:__imp_free
0x180275642  nop     dword ptr [rax+rax+00h]
0x180275647  mov     [rbx+10h], rbp
0x18027564b  mov     [rbx], rbp
0x18027564e  lea     rcx, [rsi+30h]
0x180275652  cmp     [rcx], rbp
0x180275655  jz      short loc_18027565C
0x180275657  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027565c  add     rsp, 28h
0x180275660  pop     rdi
0x180275661  pop     rsi
0x180275662  pop     rbp
0x180275663  pop     rbx
0x180275664  retn
```
