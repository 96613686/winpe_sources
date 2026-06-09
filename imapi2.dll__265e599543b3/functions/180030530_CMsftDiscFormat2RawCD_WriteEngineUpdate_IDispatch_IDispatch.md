# CMsftDiscFormat2RawCD::WriteEngineUpdate(IDispatch *,IDispatch *)

- ea: `0x180030530`
- end: `0x1800306ae`
- name: `?WriteEngineUpdate@CMsftDiscFormat2RawCD@@UEAAXPEAUIDispatch@@0@Z`
- size: `382`
- prototype: `void __fastcall(CMsftDiscFormat2RawCD *__hidden this, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800140f4`
- `0x18002df40`
- `0x18002e3a0`
- `0x180030530`
- `0x18004a010`

## pseudocode

```c
void __fastcall CMsftDiscFormat2RawCD::WriteEngineUpdate(
        CMsftDiscFormat2RawCD *this,
        struct IDispatch *a2,
        struct IDispatch *a3)
{
  struct IDispatchVtbl *lpVtbl; // rax
  int v5; // eax
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rdi
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  lpVtbl = a3->lpVtbl;
  v11 = 0;
  v10[0] = 0;
  v5 = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, _QWORD *))lpVtbl->QueryInterface)(
         a3,
         &GUID_27354136_7f64_5b0f_8f00_5d77afbe261e,
         v10);
  if ( v5 >= 0 )
  {
    v6 = ATL::CComObject<CMsftDiscFormat2RawCDEventArgs>::CreateInstance(&v11);
    v7 = v11;
    if ( v6 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v8 = *(_QWORD *)(v7 + 72);
      v9 = v10[0];
      if ( v8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        *(_QWORD *)(v7 + 72) = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      *(_QWORD *)(v7 + 72) = v9;
      *(_DWORD *)(v7 + 64) = 2;
      *(_DWORD *)(v7 + 84) = 30;
      *(_DWORD *)(v7 + 80) = 10;
      CProxy_DDiscFormat2RawCDEvents<CMsftDiscFormat2RawCD>::Fire_Update((char *)this + 24, v7);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 47),
        99,
        &WPP_465922b870433540ecd6931719c7292a_Traceguids,
        (unsigned int)v6);
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 47),
      98,
      &WPP_465922b870433540ecd6931719c7292a_Traceguids,
      (unsigned int)v5);
  }
}

```

## disassembly

```asm
0x180030530  mov     r11, rsp
0x180030533  mov     [r11+8], rbx
0x180030537  mov     [r11+10h], rsi
0x18003053b  push    rdi
0x18003053c  sub     rsp, 30h
0x180030540  mov     rax, [r8]
0x180030543  lea     rdx, _GUID_27354136_7f64_5b0f_8f00_5d77afbe261e
0x18003054a  mov     r9, r8
0x18003054d  mov     qword ptr [r11+20h], 0
0x180030555  mov     rsi, rcx
0x180030558  mov     qword ptr [r11-18h], 0
0x180030560  lea     r8, [r11-18h]
0x180030564  mov     rcx, r9
0x180030567  mov     rax, [rax]
0x18003056a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003056f  test    eax, eax
0x180030571  jns     short loc_1800305C4
0x180030573  mov     rcx, cs:WPP_GLOBAL_Control
0x18003057a  lea     rdx, WPP_GLOBAL_Control
0x180030581  cmp     rcx, rdx
0x180030584  jz      loc_18003069E
0x18003058a  test    byte ptr [rcx+184h], 4
0x180030591  jz      loc_18003069E
0x180030597  cmp     byte ptr [rcx+181h], 3
0x18003059e  jb      loc_18003069E
0x1800305a4  mov     rcx, [rcx+178h]
0x1800305ab  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x1800305b2  mov     edx, 62h ; 'b'
0x1800305b7  mov     r9d, eax
0x1800305ba  call    WPP_SF_d
0x1800305bf  jmp     loc_18003069E
0x1800305c4  lea     rcx, [rsp+38h+arg_18]
0x1800305c9  call    ?CreateInstance@?$CComObject@VCMsftDiscFormat2RawCDEventArgs@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMsftDiscFormat2RawCDEventArgs>::CreateInstance(ATL::CComObject<CMsftDiscFormat2RawCDEventArgs> * *)
0x1800305ce  mov     rbx, [rsp+38h+arg_18]
0x1800305d3  test    eax, eax
0x1800305d5  jns     short loc_180030625
0x1800305d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305de  lea     rdx, WPP_GLOBAL_Control
0x1800305e5  cmp     rcx, rdx
0x1800305e8  jz      loc_18003068A
0x1800305ee  test    byte ptr [rcx+184h], 4
0x1800305f5  jz      loc_18003068A
0x1800305fb  cmp     byte ptr [rcx+181h], 4
0x180030602  jb      loc_18003068A
0x180030608  mov     rcx, [rcx+178h]
0x18003060f  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030616  mov     edx, 63h ; 'c'
0x18003061b  mov     r9d, eax
0x18003061e  call    WPP_SF_d
0x180030623  jmp     short loc_18003068A
0x180030625  mov     rax, [rbx]
0x180030628  mov     rcx, rbx
0x18003062b  mov     rax, [rax+8]
0x18003062f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030634  mov     rcx, [rbx+48h]
0x180030638  mov     rdi, [rsp+38h+var_18]
0x18003063d  test    rcx, rcx
0x180030640  jz      short loc_180030656
0x180030642  mov     rax, [rcx]
0x180030645  mov     rax, [rax+10h]
0x180030649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003064e  mov     qword ptr [rbx+48h], 0
0x180030656  mov     rax, [rdi]
0x180030659  mov     rcx, rdi
0x18003065c  mov     rax, [rax+8]
0x180030660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030665  mov     [rbx+48h], rdi
0x180030669  lea     rcx, [rsi+18h]
0x18003066d  mov     dword ptr [rbx+40h], 2
0x180030674  mov     rdx, rbx
0x180030677  mov     dword ptr [rbx+54h], 1Eh
0x18003067e  mov     dword ptr [rbx+50h], 0Ah
0x180030685  call    ?Fire_Update@?$CProxy_DDiscFormat2RawCDEvents@VCMsftDiscFormat2RawCD@@@@QEAAXPEAUIDiscFormat2RawCDEventArgs@@@Z; CProxy_DDiscFormat2RawCDEvents<CMsftDiscFormat2RawCD>::Fire_Update(IDiscFormat2RawCDEventArgs *)
0x18003068a  test    rbx, rbx
0x18003068d  jz      short loc_18003069E
0x18003068f  mov     rax, [rbx]
0x180030692  mov     rcx, rbx
0x180030695  mov     rax, [rax+10h]
0x180030699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003069e  mov     rbx, [rsp+38h+arg_0]
0x1800306a3  mov     rsi, [rsp+38h+arg_8]
0x1800306a8  add     rsp, 30h
0x1800306ac  pop     rdi
0x1800306ad  retn
```
