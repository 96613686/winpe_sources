# utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::find<void>(ETW_BUFFER_HEADER const * const &)

- ea: `0x180002f34`
- end: `0x180002fcc`
- name: `??$find@X@?$_HashTable@PEBUETW_BUFFER_HEADER@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@U?$hash@PEBUETW_BUFFER_HEADER@@@3@U?$equal_to@PEBUETW_BUFFER_HEADER@@@3@V?$allocator@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@1@AEBQEBUETW_BUFFER_HEADER@@@Z`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000603c`
- `0x1800060b4`
- `0x180007b30`

## callees

- `0x180002f34`

## pseudocode

```c
void ***__fastcall utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::find<void>(
        __int64 a1,
        void ***a2,
        _QWORD *a3)
{
  void *v3; // r11
  unsigned __int64 v4; // r8
  void **v5; // rax

  if ( Block )
  {
    v3 = (void *)*a3;
    v4 = (0xC4CEB9FE1A85EC53uLL
        * ((0xFF51AFD7ED558CCDuLL * (*a3 ^ (*a3 >> 33))) ^ ((0xFF51AFD7ED558CCDuLL * (*a3 ^ (*a3 >> 33))) >> 33)))
       ^ ((0xC4CEB9FE1A85EC53uLL
         * ((0xFF51AFD7ED558CCDuLL * (*a3 ^ (*a3 >> 33))) ^ ((0xFF51AFD7ED558CCDuLL * (*a3 ^ (*a3 >> 33))) >> 33))) >> 33);
    v5 = (void **)*((_QWORD *)Block + 2 * (v4 & ((8LL << byte_18001D080) - 1)));
    if ( v5 )
    {
      while ( v5 != **((void ****)Block + 2 * (v4 & ((8LL << byte_18001D080) - 1)) + 1) )
      {
        if ( (unsigned __int64)v5[2] >= v4 )
        {
          if ( (unsigned __int64)v5[2] > v4 )
            break;
          if ( v3 == v5[3] )
            goto LABEL_10;
        }
        v5 = (void **)*v5;
      }
    }
  }
  v5 = &off_18001D060;
LABEL_10:
  *a2 = v5;
  return a2;
}

```

## disassembly

```asm
0x180002f34  mov     r9, cs:Block
0x180002f3b  test    r9, r9
0x180002f3e  jz      short loc_180002FBE
0x180002f40  mov     r11, [r8]
0x180002f43  mov     rcx, 0FF51AFD7ED558CCDh
0x180002f4d  mov     rax, r11
0x180002f50  mov     r10d, 8
0x180002f56  shr     rax, 21h
0x180002f5a  xor     rax, r11
0x180002f5d  imul    rax, rcx
0x180002f61  mov     rcx, rax
0x180002f64  shr     rcx, 21h
0x180002f68  xor     rcx, rax
0x180002f6b  mov     rax, 0C4CEB9FE1A85EC53h
0x180002f75  imul    rcx, rax
0x180002f79  mov     r8, rcx
0x180002f7c  shr     r8, 21h
0x180002f80  xor     r8, rcx
0x180002f83  mov     cl, cs:byte_18001D080
0x180002f89  shl     r10, cl
0x180002f8c  dec     r10
0x180002f8f  and     r10, r8
0x180002f92  add     r10, r10
0x180002f95  mov     rax, [r9+r10*8]
0x180002f99  test    rax, rax
0x180002f9c  jz      short loc_180002FBE
0x180002f9e  mov     rcx, [r9+r10*8+8]
0x180002fa3  mov     r9, [rcx]
0x180002fa6  jmp     short loc_180002FB9
0x180002fa8  cmp     [rax+10h], r8
0x180002fac  jb      short loc_180002FB6
0x180002fae  ja      short loc_180002FBE
0x180002fb0  cmp     r11, [rax+18h]
0x180002fb4  jz      short loc_180002FC5
0x180002fb6  mov     rax, [rax]
0x180002fb9  cmp     rax, r9
0x180002fbc  jnz     short loc_180002FA8
0x180002fbe  lea     rax, off_18001D060
0x180002fc5  mov     [rdx], rax
0x180002fc8  mov     rax, rdx
0x180002fcb  retn
```
