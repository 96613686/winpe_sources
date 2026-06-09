# CMSDiscMasterObj::OnDeviceRemoved(IDispatch *,ushort *)

- ea: `0x18000cb00`
- end: `0x18000cc02`
- name: `?OnDeviceRemoved@CMSDiscMasterObj@@UEAAXPEAUIDispatch@@PEAG@Z`
- size: `258`
- prototype: `void __fastcall(CMSDiscMasterObj *__hidden this, struct IDispatch *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180007bd4`
- `0x18000cb00`
- `0x180010aac`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000cbcd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbcd`

## pseudocode

```c
void __fastcall CMSDiscMasterObj::OnDeviceRemoved(CMSDiscMasterObj *this, struct IDispatch *a2, char *a3)
{
  _QWORD *v4; // rcx
  int v6; // eax
  signed __int64 v7; // rdx
  int v8; // ecx
  int v9; // eax
  __int64 v10; // rcx
  BSTR bstrString; // [rsp+30h] [rbp+8h] BYREF

  bstrString = 0;
  v4 = (_QWORD *)*((_QWORD *)this + 60);
  if ( v4 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v4 + 112LL))(*v4, &bstrString);
    if ( v6 >= 0 )
    {
      v7 = (char *)bstrString - a3;
      do
      {
        v8 = *(unsigned __int16 *)&a3[v7];
        v9 = *(unsigned __int16 *)a3 - v8;
        if ( v9 )
          break;
        a3 += 2;
      }
      while ( v8 );
      if ( !v9 )
      {
        v10 = *((_QWORD *)this + 59);
        if ( v10 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          *((_QWORD *)this + 59) = 0;
        }
        *((_QWORD *)this + 60) = 0;
        *((_BYTE *)this + 184) = 1;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        89,
        &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids,
        (unsigned int)v6);
    }
    SysFreeString(bstrString);
  }
  if ( *((_DWORD *)this + 51) )
  {
    *((_DWORD *)this + 73) |= 0x20000u;
    *((_DWORD *)this + 72) = 1;
  }
  CMyUpdateList::UpdateAll((CMSDiscMasterObj *)((char *)this + 192));
}

```

## disassembly

```asm
0x18000cb00  mov     [rsp+arg_8], rbx
0x18000cb05  push    rdi
0x18000cb06  sub     rsp, 20h
0x18000cb0a  mov     rbx, rcx
0x18000cb0d  mov     [rsp+28h+bstrString], 0
0x18000cb16  mov     rcx, [rcx+1E0h]
0x18000cb1d  mov     rdi, r8
0x18000cb20  test    rcx, rcx
0x18000cb23  jz      loc_18000CBD3
0x18000cb29  mov     rcx, [rcx]
0x18000cb2c  lea     rdx, [rsp+28h+bstrString]
0x18000cb31  mov     rax, [rcx]
0x18000cb34  mov     rax, [rax+70h]
0x18000cb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb3d  test    eax, eax
0x18000cb3f  jns     short loc_18000CB74
0x18000cb41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb48  lea     rdx, WPP_GLOBAL_Control
0x18000cb4f  cmp     rcx, rdx
0x18000cb52  jz      short loc_18000CBC8
0x18000cb54  test    byte ptr [rcx+44h], 1
0x18000cb58  jz      short loc_18000CBC8
0x18000cb5a  mov     rcx, [rcx+38h]
0x18000cb5e  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000cb65  mov     edx, 59h ; 'Y'
0x18000cb6a  mov     r9d, eax
0x18000cb6d  call    WPP_SF_d
0x18000cb72  jmp     short loc_18000CBC8
0x18000cb74  mov     rdx, [rsp+28h+bstrString]
0x18000cb79  sub     rdx, rdi
0x18000cb7c  movzx   eax, word ptr [rdi]
0x18000cb7f  movzx   ecx, word ptr [rdi+rdx]
0x18000cb83  sub     eax, ecx
0x18000cb85  jnz     short loc_18000CB8F
0x18000cb87  add     rdi, 2
0x18000cb8b  test    ecx, ecx
0x18000cb8d  jnz     short loc_18000CB7C
0x18000cb8f  test    eax, eax
0x18000cb91  jnz     short loc_18000CBC8
0x18000cb93  mov     rcx, [rbx+1D8h]
0x18000cb9a  test    rcx, rcx
0x18000cb9d  jz      short loc_18000CBB6
0x18000cb9f  mov     rax, [rcx]
0x18000cba2  mov     rax, [rax+10h]
0x18000cba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbab  mov     qword ptr [rbx+1D8h], 0
0x18000cbb6  mov     qword ptr [rbx+1E0h], 0
0x18000cbc1  mov     byte ptr [rbx+0B8h], 1
0x18000cbc8  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18000cbcd  call    cs:__imp_SysFreeString
0x18000cbd3  lea     rcx, [rbx+0C0h]; this
0x18000cbda  cmp     dword ptr [rcx+0Ch], 0
0x18000cbde  jz      short loc_18000CBF2
0x18000cbe0  bts     dword ptr [rbx+124h], 11h
0x18000cbe8  mov     dword ptr [rbx+120h], 1
0x18000cbf2  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x18000cbf7  mov     rbx, [rsp+28h+arg_8]
0x18000cbfc  add     rsp, 20h
0x18000cc00  pop     rdi
0x18000cc01  retn
```
