# wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x1800075a0`
- end: `0x18000790c`
- name: `?NotifyFailure@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `876`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800012bc`
- `0x180001560`
- `0x18000705c`
- `0x1800075a0`
- `0x180007c04`
- `0x180008630`
- `0x18000b010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800078f9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800078f9`

## pseudocode

```c
char __fastcall wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // r9
  __int64 v6; // rax
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rax
  __int64 v11; // r8
  _DWORD *v12; // rax
  int v13; // edx
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  __int64 v17; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v18; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v26; // [rsp+100h] [rbp-30h] BYREF
  __int64 v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  int v30; // [rsp+148h] [rbp+18h] BYREF
  int v31; // [rsp+150h] [rbp+20h] BYREF
  int v32; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v8 = MS3DPrintShellExtension::Provider();
      v9 = v8;
      if ( *(_DWORD *)v8 > 2u )
      {
        v10 = *((_QWORD *)v8 + 3);
        if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
        {
          v25 = *((_QWORD *)a2 + 6);
          LODWORD(SRWLock) = a2[17];
          v30 = a2[4];
          v24 = *((_QWORD *)a2 + 15);
          v11 = a1[34];
          v23 = *((_QWORD *)a2 + 14);
          v31 = a2[26];
          v22 = *((_QWORD *)a2 + 12);
          v21 = *((_QWORD *)a2 + 11);
          v32 = a2[20];
          v20 = *((_QWORD *)a2 + 9);
          v16 = a2[8];
          v19 = *((_QWORD *)a2 + 3);
          v15 = *a2;
          v26 = *((_QWORD *)a2 + 16);
          LODWORD(v17) = a2[16];
          v27 = *((_QWORD *)a2 + 7);
          LODWORD(v18) = a2[2];
          v28[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)v9,
            (unsigned int)&dword_18000DF34,
            v11 + 8,
            (_DWORD)v9,
            (__int64)v28,
            (__int64)&v18,
            (__int64)&v27,
            (__int64)&v17,
            (__int64)&v26,
            (__int64)&v15,
            (__int64)&v19,
            (__int64)&v16,
            (__int64)&v20,
            (__int64)&v32,
            (__int64)&v21,
            (__int64)&v22,
            (__int64)&v31,
            (__int64)&v23,
            (__int64)&v24,
            (__int64)&v30,
            (__int64)&SRWLock,
            (__int64)&v25);
        }
      }
    }
    else
    {
      v4 = MS3DPrintShellExtension::Provider();
      v5 = v4;
      if ( *(_DWORD *)v4 > 2u )
      {
        v6 = *((_QWORD *)v4 + 3);
        if ( (*((_QWORD *)v5 + 2) & 0x600000000000LL) != 0 && (v6 & 0x600000000000LL) == v6 )
        {
          v7 = a1[34];
          v18 = *((_QWORD *)a2 + 15);
          v17 = *((_QWORD *)a2 + 14);
          LODWORD(SRWLock) = a2[26];
          v19 = *((_QWORD *)a2 + 12);
          v20 = *((_QWORD *)a2 + 11);
          v30 = a2[20];
          v21 = *((_QWORD *)a2 + 9);
          v31 = a2[8];
          v22 = *((_QWORD *)a2 + 3);
          v32 = *a2;
          v23 = *((_QWORD *)a2 + 16);
          v15 = a2[16];
          v24 = *((_QWORD *)a2 + 7);
          v16 = a2[2];
          v25 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v5,
            (unsigned int)&unk_18000DC08,
            v7 + 8,
            (_DWORD)v5,
            (__int64)&v25,
            (__int64)&v16,
            (__int64)&v24,
            (__int64)&v15,
            (__int64)&v23,
            (__int64)&v32,
            (__int64)&v22,
            (__int64)&v31,
            (__int64)&v21,
            (__int64)&v30,
            (__int64)&v20,
            (__int64)&v19,
            (__int64)&SRWLock,
            (__int64)&v17,
            (__int64)&v18);
        }
      }
    }
  }
  wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v12 = (_DWORD *)a1[34];
  v13 = a2[2];
  if ( v13 != v12[22] && (v13 != v12[18] || (int)v12[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v12 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x1800075a0  push    rbp
0x1800075a2  push    rbx
0x1800075a3  push    rdi
0x1800075a4  lea     rbp, [rsp+10h]
0x1800075a9  sub     rsp, 120h
0x1800075b0  test    byte ptr [rdx+4], 2
0x1800075b4  mov     rbx, rdx
0x1800075b7  mov     rdi, rcx
0x1800075ba  jnz     loc_1800078BE
0x1800075c0  mov     rax, [rcx]
0x1800075c3  mov     edx, [rdx+10h]
0x1800075c6  mov     rax, [rax+10h]
0x1800075ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075cf  test    al, al
0x1800075d1  jnz     loc_180007731
0x1800075d7  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x1800075dc  mov     r9, rax
0x1800075df  mov     ecx, [rax]
0x1800075e1  cmp     ecx, 2
0x1800075e4  jbe     loc_1800078BE
0x1800075ea  mov     rax, [rax+18h]
0x1800075ee  mov     rdx, 600000000000h
0x1800075f8  mov     rcx, [r9+10h]
0x1800075fc  test    rdx, rcx
0x1800075ff  jz      loc_1800078BE
0x180007605  mov     rcx, rax
0x180007608  and     rcx, rdx
0x18000760b  cmp     rcx, rax
0x18000760e  jnz     loc_1800078BE
0x180007614  mov     rax, [rbx+78h]
0x180007618  lea     rdx, unk_18000DC08
0x18000761f  mov     r8, [rdi+110h]
0x180007626  mov     rcx, r9
0x180007629  mov     [rbp+var_70], rax
0x18000762d  add     r8, 8
0x180007631  mov     rax, [rbx+70h]
0x180007635  mov     [rbp+var_78], rax
0x180007639  mov     eax, [rbx+68h]
0x18000763c  mov     dword ptr [rbp+SRWLock], eax
0x18000763f  mov     rax, [rbx+60h]
0x180007643  mov     [rbp+var_68], rax
0x180007647  mov     rax, [rbx+58h]
0x18000764b  mov     [rbp+var_60], rax
0x18000764f  mov     eax, [rbx+50h]
0x180007652  mov     [rbp+arg_8], eax
0x180007655  mov     rax, [rbx+48h]
0x180007659  mov     [rbp+var_58], rax
0x18000765d  mov     eax, [rbx+20h]
0x180007660  mov     [rbp+arg_10], eax
0x180007663  mov     rax, [rbx+18h]
0x180007667  mov     [rbp+var_50], rax
0x18000766b  mov     eax, [rbx]
0x18000766d  mov     [rbp+arg_18], eax
0x180007670  mov     rax, [rbx+80h]
0x180007677  mov     [rbp+var_48], rax
0x18000767b  mov     eax, [rbx+40h]
0x18000767e  mov     [rbp+var_80], eax
0x180007681  mov     rax, [rbx+38h]
0x180007685  mov     [rbp+var_40], rax
0x180007689  mov     eax, [rbx+8]
0x18000768c  mov     [rbp+var_7C], eax
0x18000768f  lea     rax, [rbp+var_70]
0x180007693  mov     [rsp+130h+var_A0], rax
0x18000769b  lea     rax, [rbp+var_78]
0x18000769f  mov     [rsp+130h+var_A8], rax
0x1800076a7  lea     rax, [rbp+SRWLock]
0x1800076ab  mov     [rsp+130h+var_B0], rax
0x1800076b3  lea     rax, [rbp+var_68]
0x1800076b7  mov     [rsp+130h+var_B8], rax
0x1800076bc  lea     rax, [rbp+var_60]
0x1800076c0  mov     [rsp+130h+var_C0], rax
0x1800076c5  lea     rax, [rbp+arg_8]
0x1800076c9  mov     [rsp+130h+var_C8], rax
0x1800076ce  lea     rax, [rbp+var_58]
0x1800076d2  mov     [rsp+130h+var_D0], rax
0x1800076d7  lea     rax, [rbp+arg_10]
0x1800076db  mov     [rsp+130h+var_D8], rax
0x1800076e0  lea     rax, [rbp+var_50]
0x1800076e4  mov     [rsp+130h+var_E0], rax
0x1800076e9  lea     rax, [rbp+arg_18]
0x1800076ed  mov     [rsp+130h+var_E8], rax
0x1800076f2  lea     rax, [rbp+var_48]
0x1800076f6  mov     [rsp+130h+var_F0], rax
0x1800076fb  lea     rax, [rbp+var_80]
0x1800076ff  mov     [rsp+130h+var_F8], rax
0x180007704  lea     rax, [rbp+var_40]
0x180007708  mov     [rsp+130h+var_100], rax
0x18000770d  lea     rax, [rbp+var_7C]
0x180007711  mov     [rsp+130h+var_108], rax
0x180007716  lea     rax, [rbp+var_38]
0x18000771a  mov     [rsp+130h+var_110], rax
0x18000771f  mov     [rbp+var_38], 1000000h
0x180007727  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000772c  jmp     loc_1800078BE
0x180007731  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x180007736  mov     r9, rax
0x180007739  mov     ecx, [rax]
0x18000773b  cmp     ecx, 2
0x18000773e  jbe     loc_1800078BE
0x180007744  mov     rax, [rax+18h]
0x180007748  mov     rdx, 400000000000h
0x180007752  mov     rcx, [r9+10h]
0x180007756  test    rdx, rcx
0x180007759  jz      loc_1800078BE
0x18000775f  mov     rcx, rax
0x180007762  and     rcx, rdx
0x180007765  cmp     rcx, rax
0x180007768  jnz     loc_1800078BE
0x18000776e  mov     rax, [rbx+30h]
0x180007772  lea     rdx, dword_18000DF34
0x180007779  mov     [rbp+var_38], rax
0x18000777d  mov     rcx, r9
0x180007780  mov     eax, [rbx+44h]
0x180007783  mov     dword ptr [rbp+SRWLock], eax
0x180007786  mov     eax, [rbx+10h]
0x180007789  mov     [rbp+arg_8], eax
0x18000778c  mov     rax, [rbx+78h]
0x180007790  mov     [rbp+var_40], rax
0x180007794  mov     rax, [rbx+70h]
0x180007798  mov     r8, [rdi+110h]
0x18000779f  mov     [rbp+var_48], rax
0x1800077a3  add     r8, 8
0x1800077a7  mov     eax, [rbx+68h]
0x1800077aa  mov     [rbp+arg_10], eax
0x1800077ad  mov     rax, [rbx+60h]
0x1800077b1  mov     [rbp+var_50], rax
0x1800077b5  mov     rax, [rbx+58h]
0x1800077b9  mov     [rbp+var_58], rax
0x1800077bd  mov     eax, [rbx+50h]
0x1800077c0  mov     [rbp+arg_18], eax
0x1800077c3  mov     rax, [rbx+48h]
0x1800077c7  mov     [rbp+var_60], rax
0x1800077cb  mov     eax, [rbx+20h]
0x1800077ce  mov     [rbp+var_7C], eax
0x1800077d1  mov     rax, [rbx+18h]
0x1800077d5  mov     [rbp+var_68], rax
0x1800077d9  mov     eax, [rbx]
0x1800077db  mov     [rbp+var_80], eax
0x1800077de  mov     rax, [rbx+80h]
0x1800077e5  mov     [rbp+var_30], rax
0x1800077e9  mov     eax, [rbx+40h]
0x1800077ec  mov     dword ptr [rbp+var_78], eax
0x1800077ef  mov     rax, [rbx+38h]
0x1800077f3  mov     [rbp+var_28], rax
0x1800077f7  mov     eax, [rbx+8]
0x1800077fa  mov     dword ptr [rbp+var_70], eax
0x1800077fd  lea     rax, [rbp+var_38]
0x180007801  mov     [rsp+130h+var_88], rax
0x180007809  lea     rax, [rbp+SRWLock]
0x18000780d  mov     [rsp+130h+var_90], rax
0x180007815  lea     rax, [rbp+arg_8]
0x180007819  mov     [rsp+130h+var_98], rax
0x180007821  lea     rax, [rbp+var_40]
0x180007825  mov     [rsp+130h+var_A0], rax
0x18000782d  lea     rax, [rbp+var_48]
0x180007831  mov     [rsp+130h+var_A8], rax
0x180007839  lea     rax, [rbp+arg_10]
0x18000783d  mov     [rsp+130h+var_B0], rax
0x180007845  lea     rax, [rbp+var_50]
0x180007849  mov     [rsp+130h+var_B8], rax
0x18000784e  lea     rax, [rbp+var_58]
0x180007852  mov     [rsp+130h+var_C0], rax
0x180007857  lea     rax, [rbp+arg_18]
0x18000785b  mov     [rsp+130h+var_C8], rax
0x180007860  lea     rax, [rbp+var_60]
0x180007864  mov     [rsp+130h+var_D0], rax
0x180007869  lea     rax, [rbp+var_7C]
0x18000786d  mov     [rsp+130h+var_D8], rax
0x180007872  lea     rax, [rbp+var_68]
0x180007876  mov     [rsp+130h+var_E0], rax
0x18000787b  lea     rax, [rbp+var_80]
0x18000787f  mov     [rsp+130h+var_E8], rax
0x180007884  lea     rax, [rbp+var_30]
0x180007888  mov     [rsp+130h+var_F0], rax
0x18000788d  lea     rax, [rbp+var_78]
0x180007891  mov     [rsp+130h+var_F8], rax
0x180007896  lea     rax, [rbp+var_28]
0x18000789a  mov     [rsp+130h+var_100], rax
0x18000789f  lea     rax, [rbp+var_70]
0x1800078a3  mov     [rsp+130h+var_108], rax
0x1800078a8  lea     rax, [rbp+var_20]
0x1800078ac  mov     [rsp+130h+var_110], rax
0x1800078b1  mov     [rbp+var_20], 1000000h
0x1800078b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800078be  lea     rdx, [rbp+SRWLock]
0x1800078c2  mov     rcx, rdi
0x1800078c5  call    ?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800078ca  mov     rax, [rdi+110h]
0x1800078d1  mov     edx, [rbx+8]
0x1800078d4  lea     rcx, [rax+50h]; this
0x1800078d8  cmp     edx, [rcx+8]
0x1800078db  jz      short loc_1800078F0
0x1800078dd  cmp     edx, [rax+48h]
0x1800078e0  jnz     short loc_1800078E8
0x1800078e2  cmp     dword ptr [rax+48h], 0
0x1800078e6  jl      short loc_1800078F0
0x1800078e8  mov     rdx, rbx; struct wil::FailureInfo *
0x1800078eb  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x1800078f0  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800078f4  test    rcx, rcx
0x1800078f7  jz      short loc_1800078FF
0x1800078f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078ff  mov     al, 1
0x180007901  add     rsp, 120h
0x180007908  pop     rdi
0x180007909  pop     rbx
0x18000790a  pop     rbp
0x18000790b  retn
```
