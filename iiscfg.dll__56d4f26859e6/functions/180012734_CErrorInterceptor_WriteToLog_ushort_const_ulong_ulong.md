# CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)

- ea: `0x180012734`
- end: `0x18001293a`
- name: `?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z`
- size: `518`
- prototype: `int __fastcall(CErrorInterceptor *this, const unsigned __int16 *, int, int)`
- caller_count: `26`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800043f0`
- `0x180005cb8`
- `0x180005fdc`
- `0x180006750`
- `0x180009acc`
- `0x180009e84`
- `0x18000a1c8`
- `0x18000a9b4`
- `0x18000ce00`
- `0x18000d110`
- `0x180015f34`
- `0x180017e84`
- `0x180019128`
- `0x1800199c8`
- `0x180019f9c`
- `0x18001b188`
- `0x18001b82c`
- `0x18001bd60`
- `0x18001c86c`
- `0x18001d2a0`
- `0x18001d604`
- `0x18001da08`
- `0x18001dd08`
- `0x1800234ac`
- `0x180028868`
- `0x18002ea35`

## callees

- `0x180001f70`
- `0x18001184c`
- `0x180012224`
- `0x1800125d0`
- `0x180012734`
- `0x180030010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001276d`
- `msvcrt!swprintf_s` at `0x18001276d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012888`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012888`

## pseudocode

```c
int __fastcall CErrorInterceptor::WriteToLog(CErrorInterceptor *this, const unsigned __int16 *a2, int a3, int a4)
{
  int result; // eax
  unsigned int v7; // edx
  unsigned int *v8; // r8
  unsigned int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edi
  int v15; // eax
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  result = *(_DWORD *)this;
  if ( *(int *)this >= 0 )
  {
    swprintf_s((wchar_t *const)(*((_QWORD *)this + 1) + 9652LL), 0x100u, L"%s (%d)", a2, a3);
    *(_QWORD *)(*((_QWORD *)this + 1) + 184LL) = *((_QWORD *)this + 1) + 9652LL;
    *(_QWORD *)(*((_QWORD *)this + 1) + 160LL) = 0;
    FillInInsertionString5(
      (unsigned __int16 *)(*((_QWORD *)this + 1) + 21044LL),
      v7,
      (struct tDETAILEDERRORSRow *)(*((_QWORD *)this + 1) + 16LL));
    CErrorInterceptor::SetDescription(this);
    v10 = *((_QWORD *)this + 1);
    if ( !*(_QWORD *)(v10 + 288) )
      goto LABEL_9;
    if ( (a4 & 0x400000) == 0 )
      goto LABEL_9;
    LODWORD(v17) = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v10 + 296) + 72LL))(*(_QWORD *)(v10 + 296), 1);
    *(_DWORD *)this = result;
    if ( result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 1) + 288LL) + 72LL))(
                 *(_QWORD *)(*((_QWORD *)this + 1) + 288LL),
                 &v17);
      *(_DWORD *)this = result;
      if ( result >= 0 )
      {
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 288LL) + 88LL))(
                   *(_QWORD *)(*((_QWORD *)this + 1) + 288LL),
                   (unsigned int)v17,
                   29);
        *(_DWORD *)this = result;
        if ( result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 296LL) + 80LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 296LL));
          *(_DWORD *)this = result;
          if ( result >= 0 )
          {
            result = SetErrorInfo(0, *(IErrorInfo **)(*((_QWORD *)this + 1) + 280LL));
            *(_DWORD *)this = result;
            if ( result >= 0 )
            {
LABEL_9:
              v11 = *((_QWORD *)this + 1);
              v12 = *(_QWORD *)(v11 + 272);
              if ( v12 )
              {
                if ( (a4 & 0x800000) == 0 )
                {
                  v17 = 0;
                  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 48LL))(v12, &v17);
                  *(_DWORD *)this = v13;
                  v14 = v13;
                  if ( v13 < 0
                    || (v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD, __int64))(*(_QWORD *)v17 + 24LL))(
                                v17,
                                0,
                                0,
                                29,
                                0,
                                *((_QWORD *)this + 1) + 16LL),
                        *(_DWORD *)this = v15,
                        v14 = v15,
                        v15 < 0) )
                  {
                    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v17);
                    return v14;
                  }
                  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v17);
                }
                return 0;
              }
              else
              {
                return TErrorLogWriter::WriteDetailedErrors(0, (struct tDETAILEDERRORSRow *)(v11 + 16), v8, v9);
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012734  mov     [rsp+arg_8], rbx
0x180012739  push    rdi
0x18001273a  sub     rsp, 40h
0x18001273e  mov     eax, [rcx]
0x180012740  mov     edi, r9d
0x180012743  mov     rbx, rcx
0x180012746  test    eax, eax
0x180012748  js      loc_18001292F
0x18001274e  mov     rcx, [rcx+8]
0x180012752  mov     r9, rdx
0x180012755  mov     dword ptr [rsp+48h+var_28], r8d
0x18001275a  add     rcx, 25B4h; Buffer
0x180012761  lea     r8, aSD; "%s (%d)"
0x180012768  mov     edx, 100h; BufferCount
0x18001276d  call    cs:__imp_swprintf_s
0x180012773  mov     rcx, [rbx+8]
0x180012777  lea     rax, [rcx+25B4h]
0x18001277e  mov     [rcx+0B8h], rax
0x180012785  mov     rax, [rbx+8]
0x180012789  mov     qword ptr [rax+0A0h], 0
0x180012794  mov     rcx, [rbx+8]
0x180012798  lea     r8, [rcx+10h]; struct tDETAILEDERRORSRow *
0x18001279c  add     rcx, 5234h; unsigned __int16 *
0x1800127a3  call    ?FillInInsertionString5@@YAXPEAGKAEAUtDETAILEDERRORSRow@@@Z; FillInInsertionString5(ushort *,ulong,tDETAILEDERRORSRow &)
0x1800127a8  mov     rcx, rbx; this
0x1800127ab  call    ?SetDescription@CErrorInterceptor@@AEAAXXZ; CErrorInterceptor::SetDescription(void)
0x1800127b0  mov     rcx, [rbx+8]
0x1800127b4  cmp     qword ptr [rcx+120h], 0
0x1800127bc  jz      loc_180012898
0x1800127c2  bt      edi, 16h
0x1800127c6  jnb     loc_180012898
0x1800127cc  mov     dword ptr [rsp+48h+arg_0], 0
0x1800127d4  mov     edx, 1
0x1800127d9  mov     rcx, [rcx+128h]
0x1800127e0  mov     rax, [rcx]
0x1800127e3  mov     rax, [rax+48h]
0x1800127e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ec  mov     [rbx], eax
0x1800127ee  test    eax, eax
0x1800127f0  js      loc_18001292F
0x1800127f6  mov     rax, [rbx+8]
0x1800127fa  lea     rdx, [rsp+48h+arg_0]
0x1800127ff  mov     rcx, [rax+120h]
0x180012806  mov     rax, [rcx]
0x180012809  mov     rax, [rax+48h]
0x18001280d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012812  mov     [rbx], eax
0x180012814  test    eax, eax
0x180012816  js      loc_18001292F
0x18001281c  mov     rdx, [rbx+8]
0x180012820  xor     r9d, r9d
0x180012823  mov     rcx, [rdx+120h]
0x18001282a  lea     r8d, [r9+1Dh]
0x18001282e  add     rdx, 10h
0x180012832  mov     [rsp+48h+var_20], rdx
0x180012837  mov     edx, dword ptr [rsp+48h+arg_0]
0x18001283b  mov     rax, [rcx]
0x18001283e  mov     [rsp+48h+var_28], 0
0x180012847  mov     rax, [rax+58h]
0x18001284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012850  mov     [rbx], eax
0x180012852  test    eax, eax
0x180012854  js      loc_18001292F
0x18001285a  mov     rax, [rbx+8]
0x18001285e  mov     rcx, [rax+128h]
0x180012865  mov     rax, [rcx]
0x180012868  mov     rax, [rax+50h]
0x18001286c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012871  mov     [rbx], eax
0x180012873  test    eax, eax
0x180012875  js      loc_18001292F
0x18001287b  mov     rdx, [rbx+8]
0x18001287f  xor     ecx, ecx; dwReserved
0x180012881  mov     rdx, [rdx+118h]; perrinfo
0x180012888  call    cs:__imp_SetErrorInfo
0x18001288e  mov     [rbx], eax
0x180012890  test    eax, eax
0x180012892  js      loc_18001292F
0x180012898  mov     rdx, [rbx+8]
0x18001289c  mov     rcx, [rdx+110h]; this
0x1800128a3  test    rcx, rcx
0x1800128a6  jz      short loc_180012926
0x1800128a8  bt      edi, 17h
0x1800128ac  jb      short loc_180012922
0x1800128ae  mov     [rsp+48h+arg_0], 0
0x1800128b7  lea     rdx, [rsp+48h+arg_0]
0x1800128bc  mov     rax, [rcx]
0x1800128bf  mov     rax, [rax+30h]
0x1800128c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128c8  mov     [rbx], eax
0x1800128ca  mov     edi, eax
0x1800128cc  test    eax, eax
0x1800128ce  js      short loc_18001290A
0x1800128d0  mov     rcx, [rsp+48h+arg_0]
0x1800128d5  mov     r9d, 1Dh
0x1800128db  mov     rdx, [rbx+8]
0x1800128df  xor     r8d, r8d
0x1800128e2  add     rdx, 10h
0x1800128e6  mov     [rsp+48h+var_20], rdx
0x1800128eb  xor     edx, edx
0x1800128ed  mov     rax, [rcx]
0x1800128f0  mov     [rsp+48h+var_28], 0
0x1800128f9  mov     rax, [rax+18h]
0x1800128fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012902  mov     [rbx], eax
0x180012904  mov     edi, eax
0x180012906  test    eax, eax
0x180012908  jns     short loc_180012918
0x18001290a  lea     rcx, [rsp+48h+arg_0]
0x18001290f  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180012914  mov     eax, edi
0x180012916  jmp     short loc_18001292F
0x180012918  lea     rcx, [rsp+48h+arg_0]
0x18001291d  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180012922  xor     eax, eax
0x180012924  jmp     short loc_18001292F
0x180012926  add     rdx, 10h; struct tDETAILEDERRORSRow *
0x18001292a  call    ?WriteDetailedErrors@TErrorLogWriter@@QEAAJAEAUtDETAILEDERRORSRow@@PEAKK@Z; TErrorLogWriter::WriteDetailedErrors(tDETAILEDERRORSRow &,ulong *,ulong)
0x18001292f  mov     rbx, [rsp+48h+arg_8]
0x180012934  add     rsp, 40h
0x180012938  pop     rdi
0x180012939  retn
```
