# PoWdiPass1_TransitionTimes

- ea: `0x180004390`
- end: `0x18000451a`
- name: `PoWdiPass1_TransitionTimes`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024e8`
- `0x180004390`

## string_xrefs

- `0x180004435`: `HiberWriteTime`
- `0x180004450`: `HiberReadTime`

## pseudocode

```c
__int64 __fastcall PoWdiPass1_TransitionTimes(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  int v5; // edx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  int v8; // [rsp+20h] [rbp-20h] BYREF
  int v9; // [rsp+24h] [rbp-1Ch] BYREF
  unsigned int v10; // [rsp+28h] [rbp-18h] BYREF
  int v11; // [rsp+2Ch] [rbp-14h] BYREF
  int v12; // [rsp+30h] [rbp-10h] BYREF
  _DWORD v13[3]; // [rsp+34h] [rbp-Ch] BYREF
  int v14; // [rsp+60h] [rbp+20h] BYREF
  int v15; // [rsp+68h] [rbp+28h] BYREF

  v12 = 0;
  v13[0] = 0;
  v8 = 0;
  v11 = 0;
  v10 = 0;
  v9 = 0;
  v15 = 0;
  v14 = 0;
  result = PoWdiGetULongProperty(a1, L"SleepTime", &v14);
  if ( (_DWORD)result )
  {
    result = PoWdiGetULongProperty(a1, L"ResumeTime", &v15);
    if ( (_DWORD)result )
    {
      result = PoWdiGetULongProperty(a1, L"DriverWakeTime", &v8);
      if ( (_DWORD)result )
      {
        result = PoWdiGetULongProperty(a1, L"HiberWriteTime", &v9);
        if ( (_DWORD)result )
        {
          result = PoWdiGetULongProperty(a1, L"HiberReadTime", &v10);
          if ( (_DWORD)result )
          {
            result = PoWdiGetULongProperty(a1, L"HiberPagesWritten", &v11);
            if ( (_DWORD)result )
            {
              result = PoWdiGetULongProperty(a1, L"BiosInitTime", &v12);
              if ( (_DWORD)result )
              {
                result = PoWdiGetULongProperty(a1, L"CheckpointTime", v13);
                if ( (_DWORD)result )
                {
                  v5 = v11;
                  v6 = v10;
                  a2[5] = v14;
                  a2[6] = v15;
                  a2[7] = v8;
                  a2[8] = v9;
                  a2[12] = v12;
                  result = v13[0];
                  a2[13] = v13[0];
                  a2[9] = v6;
                  a2[10] = v5;
                  if ( v5 )
                  {
                    if ( v6 )
                    {
                      v7 = 10 * v5 / v6 + 5;
                      result = -858993459 * v7;
                      a2[11] = v7 / 0xA;
                    }
                  }
                  a2[34] |= 0x10u;
                  a2[1] |= 0x20000000u;
                }
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
0x180004390  mov     [rsp-8+arg_0], rbx
0x180004395  mov     [rsp-8+arg_8], rdi
0x18000439a  push    rbp
0x18000439b  mov     rbp, rsp
0x18000439e  sub     rsp, 40h
0x1800043a2  mov     rbx, rdx
0x1800043a5  mov     [rbp+var_10], 0
0x1800043ac  lea     rdx, aSleeptime; "SleepTime"
0x1800043b3  mov     [rbp+var_C], 0
0x1800043ba  lea     r8, [rbp+arg_10]
0x1800043be  mov     [rbp+var_20], 0
0x1800043c5  mov     rdi, rcx
0x1800043c8  mov     [rbp+var_14], 0
0x1800043cf  mov     [rbp+var_18], 0
0x1800043d6  mov     [rbp+var_1C], 0
0x1800043dd  mov     [rbp+arg_18], 0
0x1800043e4  mov     [rbp+arg_10], 0
0x1800043eb  call    PoWdiGetULongProperty
0x1800043f0  test    eax, eax
0x1800043f2  jz      loc_18000450A
0x1800043f8  lea     r8, [rbp+arg_18]
0x1800043fc  mov     rcx, rdi
0x1800043ff  lea     rdx, aResumetime; "ResumeTime"
0x180004406  call    PoWdiGetULongProperty
0x18000440b  test    eax, eax
0x18000440d  jz      loc_18000450A
0x180004413  lea     r8, [rbp+var_20]
0x180004417  mov     rcx, rdi
0x18000441a  lea     rdx, aDriverwaketime; "DriverWakeTime"
0x180004421  call    PoWdiGetULongProperty
0x180004426  test    eax, eax
0x180004428  jz      loc_18000450A
0x18000442e  lea     r8, [rbp+var_1C]
0x180004432  mov     rcx, rdi
0x180004435  lea     rdx, aHiberwritetime; "HiberWriteTime"
0x18000443c  call    PoWdiGetULongProperty
0x180004441  test    eax, eax
0x180004443  jz      loc_18000450A
0x180004449  lea     r8, [rbp+var_18]
0x18000444d  mov     rcx, rdi
0x180004450  lea     rdx, aHiberreadtime; "HiberReadTime"
0x180004457  call    PoWdiGetULongProperty
0x18000445c  test    eax, eax
0x18000445e  jz      loc_18000450A
0x180004464  lea     r8, [rbp+var_14]
0x180004468  mov     rcx, rdi
0x18000446b  lea     rdx, aHiberpageswrit; "HiberPagesWritten"
0x180004472  call    PoWdiGetULongProperty
0x180004477  test    eax, eax
0x180004479  jz      loc_18000450A
0x18000447f  lea     r8, [rbp+var_10]
0x180004483  mov     rcx, rdi
0x180004486  lea     rdx, aBiosinittime; "BiosInitTime"
0x18000448d  call    PoWdiGetULongProperty
0x180004492  test    eax, eax
0x180004494  jz      short loc_18000450A
0x180004496  lea     r8, [rbp+var_C]
0x18000449a  mov     rcx, rdi
0x18000449d  lea     rdx, aCheckpointtime; "CheckpointTime"
0x1800044a4  call    PoWdiGetULongProperty
0x1800044a9  test    eax, eax
0x1800044ab  jz      short loc_18000450A
0x1800044ad  mov     eax, [rbp+arg_10]
0x1800044b0  mov     edx, [rbp+var_14]
0x1800044b3  mov     ecx, [rbp+var_18]
0x1800044b6  mov     [rbx+14h], eax
0x1800044b9  mov     eax, [rbp+arg_18]
0x1800044bc  mov     [rbx+18h], eax
0x1800044bf  mov     eax, [rbp+var_20]
0x1800044c2  mov     [rbx+1Ch], eax
0x1800044c5  mov     eax, [rbp+var_1C]
0x1800044c8  mov     [rbx+20h], eax
0x1800044cb  mov     eax, [rbp+var_10]
0x1800044ce  mov     [rbx+30h], eax
0x1800044d1  mov     eax, [rbp+var_C]
0x1800044d4  mov     [rbx+34h], eax
0x1800044d7  mov     [rbx+24h], ecx
0x1800044da  mov     [rbx+28h], edx
0x1800044dd  test    edx, edx
0x1800044df  jz      short loc_1800044FE
0x1800044e1  test    ecx, ecx
0x1800044e3  jz      short loc_1800044FE
0x1800044e5  lea     eax, [rdx+rdx*4]
0x1800044e8  xor     edx, edx
0x1800044ea  add     eax, eax
0x1800044ec  div     ecx
0x1800044ee  lea     ecx, [rax+5]
0x1800044f1  mov     eax, 0CCCCCCCDh
0x1800044f6  mul     ecx
0x1800044f8  shr     edx, 3
0x1800044fb  mov     [rbx+2Ch], edx
0x1800044fe  or      dword ptr [rbx+88h], 10h
0x180004505  bts     dword ptr [rbx+4], 1Dh
0x18000450a  mov     rbx, [rsp+40h+arg_0]
0x18000450f  mov     rdi, [rsp+40h+arg_8]
0x180004514  add     rsp, 40h
0x180004518  pop     rbp
0x180004519  retn
```
