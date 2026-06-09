# read_markers

- ea: `0x18001a750`
- end: `0x18001aad6`
- name: `read_markers`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18001a750`
- `0x18001aadc`
- `0x18001abb0`
- `0x18001ac74`
- `0x18001af88`
- `0x18001b678`
- `0x18001bfec`
- `0x18001c3e4`
- `0x18001dc98`
- `0x18001e1b0`
- `0x180046dd4`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall read_markers(__int64 a1)
{
  __int64 v2; // rdx
  char soi; // al
  __int64 result; // rax
  char sof; // al
  char v6; // r9
  char v7; // r8
  char v8; // dl

  while ( 1 )
  {
    if ( !*(_DWORD *)(a1 + 508) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 552) + 24LL) )
      {
        if ( !(unsigned __int8)next_marker(a1) )
          return 0;
      }
      else if ( !(unsigned __int8)first_marker(a1) )
      {
        return 0;
      }
    }
    v2 = *(int *)(a1 + 508);
    if ( (_DWORD)v2 == 216 )
    {
      soi = get_soi(a1);
      goto LABEL_7;
    }
    if ( (_DWORD)v2 == 219 )
      break;
    if ( (_DWORD)v2 == 196 )
    {
      soi = get_dht((__int64 *)a1);
    }
    else
    {
      if ( (_DWORD)v2 != 239 )
      {
        switch ( (int)v2 )
        {
          case 1:
          case 208:
          case 209:
          case 210:
          case 211:
          case 212:
          case 213:
          case 214:
          case 215:
            *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 92;
            *(_DWORD *)(*(_QWORD *)a1 + 44LL) = *(_DWORD *)(a1 + 508);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 1);
            goto LABEL_8;
          case 192:
          case 193:
            v6 = 0;
            goto LABEL_23;
          case 194:
            v6 = 0;
            v8 = 1;
            v7 = 0;
            goto LABEL_27;
          case 195:
            v6 = 0;
            v7 = 1;
            goto LABEL_25;
          case 197:
          case 198:
          case 199:
          case 200:
          case 205:
          case 206:
          case 207:
            *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 60;
            goto LABEL_37;
          case 201:
            v6 = 1;
LABEL_23:
            v7 = 0;
            goto LABEL_25;
          case 202:
            v6 = 1;
            v7 = 0;
            v8 = 1;
            goto LABEL_27;
          case 203:
            v6 = 1;
            v7 = 1;
LABEL_25:
            v8 = 0;
LABEL_27:
            sof = get_sof(a1, v8, v7, v6);
            goto LABEL_13;
          case 204:
            sof = get_dac(a1);
            goto LABEL_13;
          case 217:
            *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 85;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 1);
            result = 2;
            *(_DWORD *)(a1 + 508) = 0;
            return result;
          case 218:
            if ( !get_sos((_QWORD *)a1) )
              return 0;
            *(_DWORD *)(a1 + 508) = 0;
            return 1;
          case 220:
            sof = skip_variable(a1);
            goto LABEL_13;
          case 221:
            sof = get_dri(a1);
            goto LABEL_13;
          case 224:
          case 225:
          case 226:
          case 227:
          case 228:
          case 229:
          case 230:
          case 231:
          case 232:
          case 233:
          case 234:
          case 235:
          case 236:
          case 237:
          case 238:
            break;
          case 254:
            sof = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 552) + 40LL))(a1);
            goto LABEL_13;
          default:
            *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 68;
LABEL_37:
            *(_DWORD *)(*(_QWORD *)a1 + 44LL) = *(_DWORD *)(a1 + 508);
            (**(void (__fastcall ***)(__int64))a1)(a1);
            goto LABEL_8;
        }
      }
      soi = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 552) + 8 * v2 - 1744))(a1);
    }
LABEL_7:
    if ( !soi )
      return 0;
LABEL_8:
    *(_DWORD *)(a1 + 508) = 0;
  }
  sof = get_dqt((_QWORD *)a1);
LABEL_13:
  if ( sof )
    goto LABEL_8;
  return 0;
}

```

## disassembly

```asm
0x18001a750  mov     [rsp+arg_0], rbx
0x18001a755  mov     [rsp+arg_8], rsi
0x18001a75a  push    rdi
0x18001a75b  sub     rsp, 20h
0x18001a75f  mov     rbx, rcx
0x18001a762  lea     rsi, __ImageBase
0x18001a769  xor     edi, edi
0x18001a76b  nop     dword ptr [rax+rax+00h]
0x18001a770  cmp     [rbx+1FCh], edi
0x18001a776  jz      short loc_18001A7B5
0x18001a778  movsxd  rdx, dword ptr [rbx+1FCh]
0x18001a77f  cmp     edx, 0D8h
0x18001a785  jz      short loc_18001A7A1
0x18001a787  cmp     edx, 0DBh
0x18001a78d  jz      short loc_18001A7E4
0x18001a78f  cmp     edx, 0C4h
0x18001a795  jnz     short loc_18001A802
0x18001a797  mov     rcx, rbx
0x18001a79a  call    get_dht
0x18001a79f  jmp     short loc_18001A7A9
0x18001a7a1  mov     rcx, rbx
0x18001a7a4  call    get_soi
0x18001a7a9  test    al, al
0x18001a7ab  jz      short loc_18001A7F0
0x18001a7ad  mov     [rbx+1FCh], edi
0x18001a7b3  jmp     short loc_18001A770
0x18001a7b5  mov     rax, [rbx+228h]
0x18001a7bc  mov     rcx, rbx
0x18001a7bf  cmp     [rax+18h], dil
0x18001a7c3  jnz     loc_18001A880
0x18001a7c9  call    first_marker
0x18001a7ce  test    al, al
0x18001a7d0  jnz     short loc_18001A778
0x18001a7d2  xor     eax, eax
0x18001a7d4  mov     rbx, [rsp+28h+arg_0]
0x18001a7d9  mov     rsi, [rsp+28h+arg_8]
0x18001a7de  add     rsp, 20h
0x18001a7e2  pop     rdi
0x18001a7e3  retn
0x18001a7e4  mov     rcx, rbx
0x18001a7e7  call    get_dqt
0x18001a7ec  test    al, al
0x18001a7ee  jnz     short loc_18001A7AD
0x18001a7f0  xor     eax, eax
0x18001a7f2  mov     rbx, [rsp+28h+arg_0]
0x18001a7f7  mov     rsi, [rsp+28h+arg_8]
0x18001a7fc  add     rsp, 20h
0x18001a800  pop     rdi
0x18001a801  retn
0x18001a802  cmp     edx, 0EFh
0x18001a808  jnz     short loc_18001A823
0x18001a80a  mov     rax, [rbx+228h]; jumptable 000000018001A845 cases 224-238
0x18001a811  mov     rcx, rbx
0x18001a814  mov     rax, [rax+rdx*8-6D0h]
0x18001a81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a821  jmp     short loc_18001A7A9
0x18001a823  lea     eax, [rdx-1]; switch 254 cases
0x18001a826  cmp     eax, 0FDh
0x18001a82b  ja      def_18001A845; jumptable 000000018001A845 default case, cases 2-191,196,216,219,222,223,239-253
0x18001a831  cdqe
0x18001a833  movzx   eax, ds:(byte_18001A9D8 - 180000000h)[rsi+rax]
0x18001a83b  mov     ecx, ds:(jpt_18001A845 - 180000000h)[rsi+rax*4]
0x18001a842  add     rcx, rsi
0x18001a845  jmp     rcx; switch jump
0x18001a847  mov     rax, [rbx]; jumptable 000000018001A845 case 217
0x18001a84a  mov     edx, 1
0x18001a84f  mov     rcx, rbx
0x18001a852  mov     dword ptr [rax+28h], 55h ; 'U'
0x18001a859  mov     rax, [rbx]
0x18001a85c  mov     rax, [rax+8]
0x18001a860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a865  mov     rsi, [rsp+28h+arg_8]
0x18001a86a  mov     eax, 2
0x18001a86f  mov     [rbx+1FCh], edi
0x18001a875  mov     rbx, [rsp+28h+arg_0]
0x18001a87a  add     rsp, 20h
0x18001a87e  pop     rdi
0x18001a87f  retn
0x18001a880  call    next_marker
0x18001a885  test    al, al
0x18001a887  jz      loc_18001A7F0
0x18001a88d  jmp     loc_18001A778
0x18001a892  xor     r9d, r9d; jumptable 000000018001A845 cases 192,193
0x18001a895  jmp     short loc_18001A89A
0x18001a897  mov     r9b, 1; jumptable 000000018001A845 case 201
0x18001a89a  xor     r8d, r8d
0x18001a89d  jmp     short loc_18001A8A6
0x18001a89f  mov     r9b, 1; jumptable 000000018001A845 case 203
0x18001a8a2  movzx   r8d, r9b
0x18001a8a6  xor     edx, edx
0x18001a8a8  jmp     short loc_18001A8B4
0x18001a8aa  mov     r9b, 1; jumptable 000000018001A845 case 202
0x18001a8ad  xor     r8d, r8d
0x18001a8b0  movzx   edx, r9b
0x18001a8b4  mov     rcx, rbx
0x18001a8b7  call    get_sof
0x18001a8bc  jmp     loc_18001A7EC
0x18001a8c1  xor     r9d, r9d; jumptable 000000018001A845 case 194
0x18001a8c4  mov     dl, 1
0x18001a8c6  xor     r8d, r8d
0x18001a8c9  jmp     short loc_18001A8B4
0x18001a8cb  xor     r9d, r9d; jumptable 000000018001A845 case 195
0x18001a8ce  mov     r8b, 1
0x18001a8d1  jmp     short loc_18001A8A6
0x18001a8d3  mov     rax, [rbx]; jumptable 000000018001A845 cases 197-200,205-207
0x18001a8d6  mov     dword ptr [rax+28h], 3Ch ; '<'
0x18001a8dd  jmp     short loc_18001A957
0x18001a8df  mov     rcx, rbx; jumptable 000000018001A845 case 204
0x18001a8e2  call    get_dac
0x18001a8e7  jmp     loc_18001A7EC
0x18001a8ec  mov     rcx, rbx; jumptable 000000018001A845 case 221
0x18001a8ef  call    get_dri
0x18001a8f4  jmp     loc_18001A7EC
0x18001a8f9  mov     rax, [rbx+228h]; jumptable 000000018001A845 case 254
0x18001a900  mov     rcx, rbx
0x18001a903  mov     rax, [rax+28h]
0x18001a907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a90c  jmp     loc_18001A7EC
0x18001a911  mov     rax, [rbx]; jumptable 000000018001A845 cases 1,208-215
0x18001a914  mov     edx, 1
0x18001a919  mov     dword ptr [rax+28h], 5Ch ; '\'
0x18001a920  mov     rcx, [rbx]
0x18001a923  mov     eax, [rbx+1FCh]
0x18001a929  mov     [rcx+2Ch], eax
0x18001a92c  mov     rcx, rbx
0x18001a92f  mov     rax, [rbx]
0x18001a932  mov     rax, [rax+8]
0x18001a936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a93b  jmp     loc_18001A7AD
0x18001a940  mov     rcx, rbx; jumptable 000000018001A845 case 220
0x18001a943  call    skip_variable
0x18001a948  jmp     loc_18001A7EC
0x18001a94d  mov     rax, [rbx]; jumptable 000000018001A845 default case, cases 2-191,196,216,219,222,223,239-253
0x18001a950  mov     dword ptr [rax+28h], 44h ; 'D'
0x18001a957  mov     rcx, [rbx]
0x18001a95a  mov     eax, [rbx+1FCh]
0x18001a960  mov     [rcx+2Ch], eax
0x18001a963  mov     rcx, rbx
0x18001a966  mov     rax, [rbx]
0x18001a969  mov     rax, [rax]
0x18001a96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a971  jmp     loc_18001A7AD
0x18001a976  mov     rcx, rbx; jumptable 000000018001A845 case 218
0x18001a979  call    get_sos
0x18001a97e  test    al, al
0x18001a980  jz      loc_18001A7F0
0x18001a986  mov     [rbx+1FCh], edi
0x18001a98c  mov     eax, 1
0x18001a991  jmp     loc_18001A7F2
```
