# JsonReader::ParseString(void)

- ea: `0x1400244d4`
- end: `0x1400245cc`
- name: `?ParseString@JsonReader@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140023e64`
- `0x14002410c`

## callees

- `0x14001c78c`
- `0x140023578`
- `0x1400244d4`
- `0x14002c3e8`

## pseudocode

```c
_QWORD *__fastcall JsonReader::ParseString(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r10
  __int64 v3; // r8
  __int64 v5; // r11
  __int64 v6; // rdx
  __int16 v7; // r9
  int v8; // r9d
  _BYTE pExceptionObject[32]; // [rsp+38h] [rbp-20h] BYREF

  v2 = *(unsigned int *)(a1 + 48);
  v3 = *(_QWORD *)(a1 + 40);
  if ( !*(_WORD *)(v3 + 2 * v2) )
  {
LABEL_19:
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
  v5 = 0;
  LODWORD(v6) = *(_DWORD *)(a1 + 48);
  while ( 1 )
  {
    v7 = *(_WORD *)(v3 + 2LL * (unsigned int)v6);
    if ( v7 == 92 )
    {
      ++v5;
      v6 = (unsigned int)(v6 + 1);
      *(_DWORD *)(a1 + 48) = v6;
      if ( *(_WORD *)(v3 + 2 * v6) == 117 )
      {
        v8 = 4;
        do
        {
          if ( *(_WORD *)(v3 + 2 * v6) )
          {
            v6 = (unsigned int)(v6 + 1);
            *(_DWORD *)(a1 + 48) = v6;
          }
          --v8;
        }
        while ( v8 );
        v5 += 4;
      }
      goto LABEL_11;
    }
    if ( v7 == 34 )
      break;
LABEL_11:
    if ( *(_WORD *)(v3 + 2LL * (unsigned int)v6) )
    {
      LODWORD(v6) = v6 + 1;
      *(_DWORD *)(a1 + 48) = v6;
    }
    if ( !*(_WORD *)(v3 + 2LL * (unsigned int)v6) )
      goto LABEL_19;
  }
  *(_DWORD *)(a1 + 48) = v6 + 1;
  if ( (int)v6 - 1 >= (unsigned int)v2 )
  {
    JsonReader::DecodeString(a1, a2, (unsigned int)(v6 - v2) - v5 + 1, v2, v6 - 1);
  }
  else
  {
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 7;
    *(_WORD *)a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1400244d4  mov     [rsp+arg_0], rbx
0x1400244d9  push    rdi
0x1400244da  sub     rsp, 50h
0x1400244de  mov     r10d, [rcx+30h]
0x1400244e2  xor     edi, edi
0x1400244e4  mov     r8, [rcx+28h]
0x1400244e8  mov     rbx, rdx
0x1400244eb  cmp     [r8+r10*2], di
0x1400244f0  jz      loc_1400245AB
0x1400244f6  mov     r11d, edi
0x1400244f9  mov     edx, r10d
0x1400244fc  mov     eax, edx
0x1400244fe  movzx   r9d, word ptr [r8+rax*2]
0x140024503  cmp     r9w, 5Ch ; '\'
0x140024508  jnz     short loc_140024538
0x14002450a  inc     r11
0x14002450d  inc     edx
0x14002450f  mov     [rcx+30h], edx
0x140024512  cmp     word ptr [r8+rdx*2], 75h ; 'u'
0x140024518  jnz     short loc_14002453F
0x14002451a  mov     r9d, 4
0x140024520  cmp     [r8+rdx*2], di
0x140024525  jz      short loc_14002452C
0x140024527  inc     edx
0x140024529  mov     [rcx+30h], edx
0x14002452c  sub     r9d, 1
0x140024530  jnz     short loc_140024520
0x140024532  add     r11, 4
0x140024536  jmp     short loc_14002453F
0x140024538  cmp     r9w, 22h ; '"'
0x14002453d  jz      short loc_140024558
0x14002453f  mov     eax, edx
0x140024541  cmp     [r8+rax*2], di
0x140024546  jz      short loc_14002454D
0x140024548  inc     edx
0x14002454a  mov     [rcx+30h], edx
0x14002454d  mov     eax, edx
0x14002454f  cmp     [r8+rax*2], di
0x140024554  jz      short loc_1400245AB
0x140024556  jmp     short loc_1400244FC
0x140024558  lea     r9d, [rdx-1]
0x14002455c  lea     eax, [rdx+1]
0x14002455f  mov     [rcx+30h], eax
0x140024562  cmp     r9d, r10d
0x140024565  jnb     short loc_14002458A
0x140024567  xorps   xmm0, xmm0
0x14002456a  movups  xmmword ptr [rbx], xmm0
0x14002456d  mov     [rbx+10h], rdi
0x140024571  mov     qword ptr [rbx+18h], 7
0x140024579  mov     [rbx], di
0x14002457c  mov     rax, rbx
0x14002457f  mov     rbx, [rsp+58h+arg_0]
0x140024584  add     rsp, 50h
0x140024588  pop     rdi
0x140024589  retn
0x14002458a  mov     r8d, r9d
0x14002458d  mov     [rsp+58h+var_38], r9d
0x140024592  sub     r8d, r10d
0x140024595  mov     r9d, r10d
0x140024598  inc     r8d
0x14002459b  mov     rdx, rbx
0x14002459e  sub     r8, r11
0x1400245a1  inc     r8
0x1400245a4  call    ?DecodeString@JsonReader@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KKK@Z; JsonReader::DecodeString(unsigned __int64,ulong,ulong)
0x1400245a9  jmp     short loc_14002457C
0x1400245ab  mov     edx, 0CAA60007h; int
0x1400245b0  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1400245b5  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x1400245ba  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x1400245c1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1400245c6  call    _CxxThrowException_0
```
