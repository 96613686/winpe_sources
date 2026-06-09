# FreeProperties(tagDBPROPSET *)

- ea: `0x180077200`
- end: `0x1800772cb`
- name: `?FreeProperties@@YAXPEAUtagDBPROPSET@@@Z`
- size: `203`
- prototype: `void __fastcall(struct tagDBPROPSET *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800771ac`

## callees

- `0x180011c74`
- `0x180077200`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18007729a`
- `OLEAUT32!__imp_VariantClear` at `0x18007729a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18007726a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18007726a`
- `ole32!CoTaskMemFree` at `0x1800772bc`
- `ole32!CoTaskMemFree` at `0x1800772bc`

## pseudocode

```c
void __fastcall FreeProperties(struct tagDBPROPSET *a1)
{
  __int64 v2; // rax
  BOOL v3; // ebp
  __int64 i; // rsi
  DBPROP *rgProperties; // rax
  OLECHAR *bstrVal; // rcx
  UINT v7; // eax
  __int64 v8; // rdx
  BYTE *pbVal; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9

  if ( a1->rgProperties )
  {
    v2 = *(_QWORD *)&a1->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
    if ( !v2 )
      v2 = *(_QWORD *)a1->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
    v3 = v2 == 0;
    for ( i = 0; (unsigned int)i < a1->cProperties; i = (unsigned int)(i + 1) )
    {
      if ( v3 )
      {
        rgProperties = a1->rgProperties;
        if ( (a1->rgProperties[i].dwPropertyID == 9 || rgProperties[i].dwPropertyID == 160)
          && rgProperties[i].vValue.vt == 8 )
        {
          bstrVal = rgProperties[i].vValue.bstrVal;
          if ( bstrVal )
          {
            v7 = SysStringByteLen(bstrVal);
            v8 = v7;
            pbVal = a1->rgProperties[i].vValue.pbVal;
            if ( v7 )
            {
              do
              {
                *pbVal++ = 0;
                --v8;
              }
              while ( v8 );
            }
          }
        }
      }
      VariantClear(&a1->rgProperties[i].vValue);
      LOBYTE(v10) = 1;
      FreeDBID(&a1->rgProperties[i].colid, v10, v11, v12);
    }
    CoTaskMemFree(a1->rgProperties);
  }
}

```

## disassembly

```asm
0x180077200  push    rbx
0x180077202  push    rbp
0x180077203  push    rsi
0x180077204  push    rdi
0x180077205  sub     rsp, 28h
0x180077209  cmp     qword ptr [rcx], 0
0x18007720d  mov     rdi, rcx
0x180077210  jz      loc_1800772C2
0x180077216  mov     rax, [rcx+0Ch]
0x18007721a  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180077221  jnz     short loc_18007722E
0x180077223  mov     rax, [rcx+14h]
0x180077227  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x18007722e  xor     ebp, ebp
0x180077230  test    rax, rax
0x180077233  setz    bpl
0x180077237  xor     esi, esi
0x180077239  cmp     [rcx+8], esi
0x18007723c  jbe     short loc_1800772B9
0x18007723e  test    ebp, ebp
0x180077240  jz      short loc_18007728B
0x180077242  mov     rax, [rdi]
0x180077245  lea     rbx, [rsi+rsi*8]
0x180077249  cmp     dword ptr [rax+rbx*8], 9
0x18007724d  jz      short loc_180077258
0x18007724f  cmp     dword ptr [rax+rbx*8], 0A0h
0x180077256  jnz     short loc_18007728B
0x180077258  cmp     word ptr [rax+rbx*8+30h], 8
0x18007725e  jnz     short loc_18007728B
0x180077260  mov     rcx, [rax+rbx*8+38h]; bstr
0x180077265  test    rcx, rcx
0x180077268  jz      short loc_18007728B
0x18007726a  call    cs:__imp_SysStringByteLen
0x180077270  mov     edx, eax
0x180077272  mov     rax, [rdi]
0x180077275  mov     rcx, [rax+rbx*8+38h]
0x18007727a  test    rdx, rdx
0x18007727d  jz      short loc_18007728B
0x18007727f  mov     byte ptr [rcx], 0
0x180077282  inc     rcx
0x180077285  sub     rdx, 1
0x180077289  jnz     short loc_18007727F
0x18007728b  mov     rcx, [rdi]
0x18007728e  lea     rbx, [rsi+rsi*8]
0x180077292  add     rcx, 30h ; '0'
0x180077296  lea     rcx, [rcx+rbx*8]; pvarg
0x18007729a  call    cs:__imp_VariantClear
0x1800772a0  mov     rcx, [rdi]
0x1800772a3  mov     dl, 1; bool
0x1800772a5  add     rcx, 10h
0x1800772a9  lea     rcx, [rcx+rbx*8]; struct tagDBID *
0x1800772ad  call    ?FreeDBID@@YAXPEAUtagDBID@@_N@Z; FreeDBID(tagDBID *,bool)
0x1800772b2  inc     esi
0x1800772b4  cmp     esi, [rdi+8]
0x1800772b7  jb      short loc_18007723E
0x1800772b9  mov     rcx, [rdi]; pv
0x1800772bc  call    cs:__imp_CoTaskMemFree
0x1800772c2  add     rsp, 28h
0x1800772c6  pop     rdi
0x1800772c7  pop     rsi
0x1800772c8  pop     rbp
0x1800772c9  pop     rbx
0x1800772ca  retn
```
