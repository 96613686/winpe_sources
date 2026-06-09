# CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_CreateItemID(MEDIASERVER_ITEMID const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180008780`
- end: `0x18000889d`
- name: `?s_CreateItemID@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@SAJPEFBUMEDIASERVER_ITEMID@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800021b0`

## callees

- `0x180008780`
- `0x1800204f4`
- `0x1800333e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008882`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_CreateItemID(
        _DWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  int v5; // eax
  __int64 (__fastcall **v8)(_QWORD, GUID *, __int64 *); // rax
  __int64 result; // rax
  int v10; // ebp
  __int64 v11; // rax
  __int64 v12; // rsi
  void *v13; // rax
  unsigned int v14; // ebx
  __int64 v15[5]; // [rsp+20h] [rbp-28h] BYREF
  size_t Size; // [rsp+58h] [rbp+10h] BYREF
  void *Src; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v5 = 0;
  LODWORD(Size) = 0;
  Src = 0;
  if ( a2 )
  {
    v8 = *a2;
    v15[0] = 0;
    result = (*v8)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, v15);
    if ( (int)result < 0 )
      return result;
    v10 = (*(__int64 (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v15[0] + 40LL))(v15[0], &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15[0] + 16LL))(v15[0]);
    if ( v10 < 0 )
      return (unsigned int)v10;
    v5 = Size;
  }
  v11 = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_Alloc((unsigned int)(v5 + 12) + 2LL, a4);
  v12 = v11;
  if ( v11 )
  {
    *(_DWORD *)(v11 + 6) = 1159165815;
    *(_WORD *)(v11 + 10) = Size;
    *(_WORD *)(v11 + 12) = 4;
    if ( a1 )
      *(_DWORD *)(v11 + 14) = *a1;
    v13 = Src;
    if ( Src )
    {
      memcpy_0((void *)(v12 + 18), Src, (unsigned int)Size);
      v13 = Src;
    }
    *a3 = v12;
    v14 = 0;
  }
  else
  {
    v13 = Src;
    v14 = -2147024882;
  }
  CoTaskMemFree(v13);
  return v14;
}

```

## disassembly

```asm
0x180008780  mov     [rsp+arg_0], rbx
0x180008785  mov     [rsp+arg_18], rbp
0x18000878a  push    rsi
0x18000878b  push    rdi
0x18000878c  push    r14
0x18000878e  sub     rsp, 30h
0x180008792  xor     r14d, r14d
0x180008795  mov     rsi, r9
0x180008798  mov     [r8], r14
0x18000879b  mov     eax, r14d
0x18000879e  mov     dword ptr [rsp+48h+Size], eax
0x1800087a2  mov     rbx, r8
0x1800087a5  mov     [rsp+48h+Src], r14
0x1800087aa  mov     r10, rdx
0x1800087ad  mov     rdi, rcx
0x1800087b0  test    rdx, rdx
0x1800087b3  jz      short loc_180008812
0x1800087b5  mov     rax, [rdx]
0x1800087b8  lea     r8, [rsp+48h+var_28]
0x1800087bd  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x1800087c4  mov     [rsp+48h+var_28], r14
0x1800087c9  mov     rcx, r10
0x1800087cc  mov     rax, [rax]
0x1800087cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d4  test    eax, eax
0x1800087d6  js      loc_18000888A
0x1800087dc  mov     rcx, [rsp+48h+var_28]
0x1800087e1  lea     r8, [rsp+48h+Size]
0x1800087e6  lea     rdx, [rsp+48h+Src]
0x1800087eb  mov     rax, [rcx]
0x1800087ee  mov     rax, [rax+28h]
0x1800087f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f7  mov     rcx, [rsp+48h+var_28]
0x1800087fc  mov     ebp, eax
0x1800087fe  mov     rdx, [rcx]
0x180008801  mov     rax, [rdx+10h]
0x180008805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880a  test    ebp, ebp
0x18000880c  js      short loc_180008871
0x18000880e  mov     eax, dword ptr [rsp+48h+Size]
0x180008812  lea     ecx, [rax+0Ch]
0x180008815  mov     rdx, rsi
0x180008818  add     rcx, 2
0x18000881c  call    ?s_Alloc@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@CAPEAUCHILDITEMID@1@_KPEAUIMalloc@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_Alloc(unsigned __int64,IMalloc *)
0x180008821  mov     rsi, rax
0x180008824  test    rax, rax
0x180008827  jz      short loc_180008875
0x180008829  mov     dword ptr [rax+6], 45177777h
0x180008830  movzx   ecx, word ptr [rsp+48h+Size]
0x180008835  mov     [rax+0Ah], cx
0x180008839  mov     word ptr [rax+0Ch], 4
0x18000883f  test    rdi, rdi
0x180008842  jz      short loc_180008849
0x180008844  mov     ecx, [rdi]
0x180008846  mov     [rax+0Eh], ecx
0x180008849  mov     rax, [rsp+48h+Src]
0x18000884e  test    rax, rax
0x180008851  jz      short loc_180008869
0x180008853  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180008858  lea     rcx, [rsi+12h]; void *
0x18000885c  mov     rdx, rax; Src
0x18000885f  call    memcpy_0
0x180008864  mov     rax, [rsp+48h+Src]
0x180008869  mov     [rbx], rsi
0x18000886c  mov     ebx, r14d
0x18000886f  jmp     short loc_18000887F
0x180008871  mov     eax, ebp
0x180008873  jmp     short loc_18000888A
0x180008875  mov     rax, [rsp+48h+Src]
0x18000887a  mov     ebx, 8007000Eh
0x18000887f  mov     rcx, rax; pv
0x180008882  call    cs:__imp_CoTaskMemFree
0x180008888  mov     eax, ebx
0x18000888a  mov     rbx, [rsp+48h+arg_0]
0x18000888f  mov     rbp, [rsp+48h+arg_18]
0x180008894  add     rsp, 30h
0x180008898  pop     r14
0x18000889a  pop     rdi
0x18000889b  pop     rsi
0x18000889c  retn
```
